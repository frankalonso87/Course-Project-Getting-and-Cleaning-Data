Course Project Getting and Cleaning Data (November 2014)

Project Description

The purpose of this project is to demonstrate your ability to collect, work with, and clean a data set. The goal is to prepare tidy data that can be used for later analysis. You will be graded by your peers on a series of yes/no questions related to the project.

You will be required to submit:

a) a tidy data set as described below
b) a link to a Github repository with your script for performing the analysis
c) a code book that describes the variables, the data, and any transformations or work that you performed to clean up the data called CodeBook.md. 
d) a README.md in the repo with your scripts. This file explains how all of the scripts work and how they are connected.

One of the most exciting areas in all of data science right now is wearable computing. Companies like Fitbit, Nike, and Jawbone Up are racing to develop the most advanced algorithms to attract new users. The data linked to from the course website represent data collected from the accelerometers from the Samsung Galaxy S smartphone. A full description is available at the site where the data was obtained: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Here are the data for the project: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

You should create one R script called run_analysis.R that does the following:
a) Merges the training and the test sets to create one data set.
b) Extracts only the measurements on the mean and standard deviation for each measurement.
c) Uses descriptive activity names to name the activities in the data set
d) Appropriately labels the data set with descriptive activity names.
e) Creates a second, independent tidy data set with the average of each variable for each activity and each subject.

What you find in this repository

CodeBook.md: Information about the raw and tidy data sets and transformations made on them.

README.md: General information about the Project and instructions you have to follow in order to obtain the tidy data set.

run_analysis.R: R scipt necessary to transform the raw data set into a tidy one

How to create the tidy data set

a) clone this repository: git clone https://github.com/frankalonso87/Course-Project-Getting-and-Cleaning-Data.git
b) download compressed raw data using the link provided at the beginning of this Readme file.
c) unzip raw data and copy the resulting directory UCI HAR Dataset to the  repository you just cloned
d) open a R console and set the working directory (setwd())to be the directory containing the repo you cloned.
e) source the run_analisys.R script (pay attention as you will be required to load the plyr package) source('run_analysis.R')
f) Finally you will find  the file tidydata.txt which contains the tidy data asked in this Project.
