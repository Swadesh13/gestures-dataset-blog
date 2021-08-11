# How to use the Github code and the Singularity container

## GitHub Code

The code for my project is at [redhen-gestures](https://github.com/Swadesh13/redhen-gesture). The code is inside `src/code`. The initial def file is at `src/singualrity/openpose.def`. 

### Working of the code

Inside the code, all actions are performed from `workflow.py`. It handles both training and detection on videos. Firstly, the keypoints are obtained by running OpenPose. These keypoints are then divided on the basis of number of persons and then on the basis of continuity (i.e. detect change in camera angles/view by comparing the corresponding keypoints). For training, additionally csv annotation files are required which contain the start and end timestamps for gestures (column names are 'Begin Time - msec' and 'End Time - msec'). These will be used to generate training data based on the keypoits. For detection, only the keypoints are used to detect frames. Detection results are available in a CSV file and also in a video format where everytime there is a gesture, a small text at the upper right corner will demarcate it.

The following parameters have default values:
* window_size : 5
* max_persons (to be considered in a frame, others are discarded) : 6
* max_change_ratio (a fraction of the video dimensions that defines if 2 frames are taken from the same angle or not) : 0.025
* model_path : kept inside the container with default parameters
* if training:
  * batch_size : 16
  * epochs : 20
  * retrain : False (new model is trained)
* if detection:
  * no specific argument. If no model path is provided, then it will select the default model_path.

## Singualrity Container

The Singularity Container contains code for training and testing on gestures videos. 

### Commands

I will talk about run commands only, since run is used for utilizing Singularity containers.

To know what command line arguments are available:
```
    $ singularity run <name-of-gestures-container.sif> --help
```

#### Detection

Detection on any video file:
```
    $ singularity run --nv -B <path-to-directory-with-write-access> <name-of-gestures-container.sif> --input_files <path-to-video-file(s)> --output_dir <path-to-output_dir> detect
```

Detection on video files inside a directory:
```
    $ singularity run --nv -B <path-to-writable-directory> <name-of-gestures-container.sif> --input_dir <path-to-readable-directory> --output_dir <path-to-output_dir> detect
```

Additionally, you can detect with different parameters (note that changing window size or max persons in a frame can require a different model due to different parameters):
```
    $ singularity run --nv -B <path-to-writable-directory> <name-of-gestures-container.sif> --input_dir <path-to-readable-directory> --output_dir <path-to-output_dir> --detection_threshold 0.4 ... detect
```

For a different model (Note only Tensorflow models are accepted, which can be read by `tf.keras.models.load_model(<model_path>)`):
```
    $ singularity run --nv -B <path-to-writable-directory> <name-of-gestures-container.sif> --input_dir <path-to-readable-directory> --output_dir <path-to-output_dir> ... <parameters> --model_path <path-to-model> detect
```
#### Training

For training, the commands are similar. Training a new model:
```
    $ singularity run --nv -B <path-to-writable-directory> <name-of-gestures-container.sif> --input_dir <path-to-readable-directory> --output_dir <path-to-output_dir> ... <parameters> --model_path <path-to-model> train ... <parameters-epochs-batch_size>
```

To automatically select the default model in the container, retrain it and save the updated model in your output directory.
(keep the default parameters other wise error)
```
    $ singularity run --nv -B <path-to-writable-directory> <name-of-gestures-container.sif> --input_dir <path-to-readable-directory> --output_dir <path-to-output_dir> ... <parameters> --model_path <path-to-model> train --retrain ... <parameters>
```

Otherwise, use the model path to retrain a specific model as used in detection.