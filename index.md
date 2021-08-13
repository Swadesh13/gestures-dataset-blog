# Gesture Dataset Analysis

This blog is maintained by Swadesh Jana about the updates on the progress of GSoC 2021 project with Red Hen Lab.

For the GitHub repo of the work on this project, check here: [https://github.com/Swadesh13/redhen-gesture](https://github.com/Swadesh13/redhen-gesture)

## Useful information while beginning to work:
Some useful links on information that I had to learn and on how to use my container:
- How to use my container: Click [Here](how-to-use.md)
- HPC Information and Commands: Click [Here](HPC.md)
- Singularity Information and Commands: Click [Here](Singularity.md)


## Table of Contents:
- [Gesture Dataset Analysis](#gesture-dataset-analysis)
  - [Useful information while beginning to work:](#useful-information-while-beginning-to-work)
  - [Table of Contents:](#table-of-contents)
  - [Introduction](#introduction)
  - [Project Description](#project-description)
  - [Weekly Updates](#weekly-updates)
  - [Community Bonding Period](#community-bonding-period)
    - [Week 1 (16 - 22 May, 2021)](#week-1-16---22-may-2021)
    - [Week 2 (23 - 29 May, 2021)](#week-2-23---29-may-2021)
    - [Week 3 (30 May - 05 June, 2021)](#week-3-30-may---05-june-2021)
  - [Coding Period](#coding-period)
    - [Week 1 (06 - 12 June, 2021)](#week-1-06---12-june-2021)
    - [Week 2 (13 - 19 June, 2021)](#week-2-13---19-june-2021)
    - [Week 3 (20 - 26 June, 2021)](#week-3-20---26-june-2021)
    - [Week 4 (27 June - 3 July, 2021)](#week-4-27-june---3-july-2021)
    - [Week 5 (4 - 10 July, 2021 )](#week-5-4---10-july-2021-)
    - [Week 6 (11 - 17 July, 2021 )](#week-6-11---17-july-2021-)
    - [Week 7 (18 - 24 July, 2021 )](#week-7-18---24-july-2021-)
    - [Week 8 (25 - 31 July, 2021)](#week-8-25---31-july-2021)
    - [Week 9 (01 - 07 August, 2021)](#week-9-01---07-august-2021)
    - [Week 10 (08 - 14 August, 2021)](#week-10-08---14-august-2021)

## Introduction

Hi, I am Swadesh Jana, currently (as of May, 2021) a 2nd year under-graduate Computer Science and Engineering student at Jadavpur University, Kolkata, India. I am ethusiatic about Deep Learning, especially Computer Vision and its myriad applications on various aspects of life. Red Hen Lab's Multimodal Communication Research is a very interesting and exciting field that I would love to explore.

Contact me @
- [LinkedIn](https://www.linkedin.com/in/swadeshjana/)

## Project Description

My project is on Gesture Detection in Video Dataset annotated by experts. The first task will be to first prepare the dataset for use in gesture detection. This refined dataset will then be used for analtsis and detection using Deep Learning methods. Primarily, my focus will be on utilising the power of Pose Detection models such as OpenPose and then utilising the landmark positions to predict features such as handedness, movement type, orientation etc. (as annotated). Finally, the code will be hosted on CWRU HPC in a pipeline. 

Check proposal @ GSoC website: [Click Here](https://summerofcode.withgoogle.com/projects/#5781190964936704)

Mentors: [Peter Uhrig](https://www.angam.phil.fau.de/staff/uhrig/), [Elizabeth Mahoney](https://www.linkedin.com/in/elizabethmahoney4/)

## Weekly Updates

Here I will be writing about how I proceed with the tasks every week starting from my first Community Bonding Period to the final evaluations.

## Community Bonding Period

### Week 1 (16 - 22 May, 2021)

I received the proposal acceptance from Red Hen Lab on May 17. Next, I contacted my mentors Dr. Peter Uhrig and Elizabeth Mahoney. Also, after the initial setup of CWRU emails, I also tried accessing the HPC computing service that we were allowed to use for the project. Finally, I gave a brief of my project to my mentors and discussed on the same.

### Week 2 (23 - 29 May, 2021)

Due to my semester exams, I couldn't proceed much with the work. However, discussed with my mentor about the project so that we are on the same page. Went through certain documentations on using the HPC Computing service and the Elan software for annotations (and extracting them). The first meet of the Community was held on May 28 and we introduced ourselves and got to know Red Hen Lab. Really excited to start working with Red Hen Lab!

### Week 3 (30 May - 05 June, 2021)

One of my mentors, Elizabeth Mahoney conducted an introductory meeting about the dataset and tried to answer my questions on the dataset. Later in the week, I set up my Gallina directory required for storing all large files. I tried playing with the HPC OnDemand web portal. It's the second (and last) week of my exams.

## Coding Period

### Week 1 (06 - 12 June, 2021)

On Monday, my mentors conducted another session updating me with my week's work. The documentation of the annotations and the videos were provided to me. Also, I will study one of the documentations ([Link Here](https://frankier.github.io/skelshop/)) along with the singularity containers on Fankie's SkelShop. My work for the week will be as follows (subject to changes):
1. Rebuild the video dataset from YouTube based on Elizabeth Mahoney's instructions
2. Read the GitHub documentation 
3. Understand the working of singularity containers and check out the provided containers

Seems a busy week ahead, but it will be exciting !!!

On Tuesday, I attended Mahnaz Parian-Scherb's PhD defence meeting to get to know about her work on gestures using various Image Processing techniques and Deep Learning. I learned a lot and look forward to a private meeting with my mentors to get a more detailed understanding of OpenPose and the methods she used.

The dataset consisting of Elen DeGeneres shows' videos and gesture annotations are available through Google Drive. However, some of the videos are not available in the public on any online platform. Out of the 30 videos in the dataset, 19 are present online (in Youtube, Dailymotion), 11 are not available out of which 3 are private links while 8 are not found.

Also, I checked out the singularity containers and have some idea of how they work.

On Saturday, I had a chat with Frankie, one of the mentors at Red Hen Lab about his previous work (SkelShop). Main points of the conversation are:
1. He shared some recommendations, such as using Docker Files due to its larger community. Get them [here](https://frankie.robertson.name/research/effective-cluster-computing/)
2. He used make files, specifically SnakeMake to automate the pipelines. Study them [here](http://www.hpc-carpentry.org/hpc-python/)
3. OpenPose was used for obtaining landmark positions and he explained the pipeline and also about how OpenPose works in a nutshell. His GitHub [Repo](https://github.com/frankier/skelshop/) will be important to study.
4. Changes in shots (instantaneous change of angle, for example) was an issue in his project. Shot segmentation maybe required.

### Week 2 (13 - 19 June, 2021)

I updated my mentor Dr. Uhrig about my work uptil Sunday. My further work will be as follows:
1. Work on the dataset. Use OpenPose to get landmarks on the videos and utilise them to get certain basic predictions such as simple hand movement detection using LSTMs and/or CNNs.
2. Study SnakeMake, Docker (also, Singularity) and SkelShop's code throughly.
3. Write a mail to access Red Hen's Open Dataset (to get the actual high resolution videos).

Throughout the week, I mostly invested my time in understanding the Singularity containers and how they work and are built. I documented what I learnt [here](#useful-links). Also, I successfully built the OpenPose module (after cloning it from GitHub) and ran the videos. However, I have been unable to directly run them from the Singularity container as the first stage of the pipeline. I will do that next week.

### Week 3 (20 - 26 June, 2021)

I continued my work on using OpenPose in Singularity containers. I would like to point out that the `--sandbox` option and build an OpenPose directory is important because it allows to change or add files as required and then one can build from the directory. Also, I updated my documentation on that.

I am using Frankierr's OpenPose Docker Image file `frankierr/openpose_containers:focal_nvcaffe` for GPU support on the HPC. Also, note that the `/.openpose_env` file may not have execution access for all users. So, build the sandbox ([Check Here](/Singualrity.md)) and then using `sudo` change the execution permissions of the file. Finally, build the image file from the sandbox.

Now, I have a working OpenPose container and next week, I will get the OpenPose output on the provided dataset and use the landmarks to analyse and possibly train models.

### Week 4 (27 June - 3 July, 2021)

In my work continuing with using OpenPose containers, I made a new file named [workflow.py](https://github.com/Swadesh13/redhen-gesture/blob/main/src/code/workflow.py) which will handle all the workflow stuff. I could have used SnakeMake (as suggested by Frankie), but a simple python module will suffice for now. It handles the arguments such path to input and output directories, runs OpenPose by creating a thread using the `subprocess` module. The week was spent in creating the Container, adding the module to the sandbox (and other necessary changes briefly stated in the README of my code [repo](https://github.com/Swadesh13/redhen-gesture)) and creating a smooth workflow. Then, I got the OpenPose output from all the 30 videos to further create a training data for the deep learning model.

### Week 5 (4 - 10 July, 2021 )

Lots of updates in the code. I developed a simple strategy for using the OpenPose keypoints. It is shortly described as follows:
1. 25 Body positions are obtained from the OpenPose module. They can be found in the OpesPose docs [here](https://github.com/CMU-Perceptual-Computing-Lab/openpose/blob/master/doc/02_output.md). The values are in the form of a list of (x, y, confidence).
2. OpenPose doesn't identify persons between frames, so I used a simple methodology of identifying persons across frames. I used a simple ratio of the average dimension of the frame as a threshold. If neck positions across consecutive frames are within the threshold then they are of same person other wise different.
3. I also put a threshold to the number of persons. Frames with more than the threshold number of persons are rejected.
4. For consecutive frames which focus on the same person(s) or same angle, the frames are arranged so that they form a time series data. I aggregate consecutive n (say, n = 3) frames as a window on the keypoints for the model to predict if there is a gesture on the 3rd frame.
5. The data is of the shape, row = Keypoints (of neck, shoulder, elbow, wrist) x and y values, col = max persons in a frame (dummy value of -1 for frames with less than max persons) and depth = window size.

The data is trained on a simple Tensorflow Deep Learning model made with `ConvLSTM2D` and `Conv3D` layers and finally a `Dense` layer with `sigmoid` activation as the output.

Over the week, I wrote all the code and then trained on a sample video to check if the method is working. As a starting baseline, it provides an accuracy and precision in the range of about 70%. I also used the sample output to mark the video where the model had predicted hand gestures. In the following week, I plan to refine my model and also train on all the 30 videos.

### Week 6 (11 - 17 July, 2021 )

Model optimization begins. With the same data, I changed the layers and certain hyperparameters such as layer arrangement, and number of layers. There is a lot of overfitting. The validation accuracy does't change much from 70-71%. I also wrote code to show in which areas the model predicts that there is a gesture. Currently, searching for some previous works on this area to gain more insights.

### Week 7 (18 - 24 July, 2021 )

`Conv3D` layers in a VGG-like architecture seemed to give the best results at accuracy and precision of 72%, but there is a large overfitting. Over the week, I continued checking with various combinations. I also got to know about Optical Flow and started studying on its applications in gesture recognition. However, as Mahnaz pointed out it will detect every small change in the background as well as detect zoom on the data. So, I had to discard the idea.

### Week 8 (25 - 31 July, 2021)

After certain changes in parameters and number of layers, the precision increased to 74%. Since it is 3D data, direct LSTM layers are not compatible and even `ConvLSTM2D` did not work very well on the data (even with bidirectional). I also checked by subtracting the mean but that did not help. Also, I built the Singularity container with the model deployed in it and detections shown so that the container can be used in the future.

### Week 9 (01 - 07 August, 2021)
The final 2 weeks of GSoC begins. Even though my mentor has asked me to start wrapping and tidying up everything and prepare to showcase the projects, I will try one time to develop some kind of attention mechanism based model. After that I need to finish up with the code and Container for final review. The model will be simple. 2 consecutive frames will be input to feature extractors and then the features can be concatenated to pass through LSTMs for time dependent feature detection such as gestures. Will update with the results if successful.

The featue extractor-LSTM model was unsuccessful, it seems there is too much data (or noise) to detect a hand movement somewhere. Possibly, some more powerful architecture (encoder-decoder or similar) can be used with the image data. I might try that after cleaning up the code and my blog and all that ends. 

Also, I cleaned up the code over the weekend adding basic training and detection features to the container.

### Week 10 (08 - 14 August, 2021)

There were some debugging I had to do on the Container. Also, I wrote the pages[tl;dr](tldr.md) and [How to Use](how-to-use.md). All information on my work can be found there. Finally, I am writing a page in the techne public site to publish the dataset on Red Hen Lab.