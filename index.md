# Gesture Dataset Analysis

This blog is maintained by Swadesh Jana about the updates on the progress of GSoC 2021 project with Red Hen Lab.

## Table of Contents:
- [Gesture Dataset Analysis](#gesture-dataset-analysis)
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

I received the proposal acceptance from Red Hen Lab on May 17. Next, I contacted my mentors Dr. Peter Uhrig and Elizabeth Mahoney. Also, after the initial setup of CWRU emails, I also tried accessing the HPC computing service that we were allowed to use for the project^. Finally, I gave a brief of my project to my mentors and discussed on the same.

^Note: *Do not try to **sudo** on the cluster without priviledged access :)* 

### Week 2 (23 - 29 May, 2021)

Due to my semester exams, I couldn't proceed much with the work. However, discussed with my mentor about the project so that we are on the same page. Went through certain documentations on using the HPC Computing service and the Elan software for annotations (and extracting them). The first meet of the Community was held on May 28 and we introduced ourselves and got to know Red Hen Lab. Really excited to start working with Red Hen Lab!

### Week 3 (30 May - 05 June, 2021)

One of my mentors, Elizabeth Mahoney conducted an introductory meeting about the dataset and tried to answer my questions on the dataset. Later in the week, I set up my Gallina directory required for storing all large files. I tried playing with the HPC OnDemand web portal. It's the second (and last) week of my exams.

## Coding Period

### Week 1 (06 - 12 June, 2021)

On Tuesday, my mentors conducted another session updating me with my week's work. The documentation of the annotations and the videos were provided to me. Also, I will review one of the documentations ([Link Here](https://frankier.github.io/skelshop/)) on a similar work done previously. Finally, the singularity containers for previous projects were also shared. My work for the week will be as follows (subject to changes):
1. Go through the annotations and videos
2. Read the GitHub documentation (Fankie's SkelShop)
3. Understand the working of singularity containers and check out the provided containers

Seems a busy week ahead, but it will be exciting !!!