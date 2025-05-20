# Jenkins Basic Pipeline Assignment

## Overview

This project demonstrates how to create and monitor a basic Jenkins pipeline using a simple multi-stage workflow. The pipeline simulates common CI/CD steps: Build, Test, Deploy, and Cleanup.
This guide will help you set up Jenkins, create the pipeline job, run it, and monitor its execution.

---

## Table of Contents

* [Prerequisites](#prerequisites)
* [Setup Jenkins](#setup-jenkins)
* [Create a Pipeline Job](#create-a-pipeline-job)
* [Pipeline Script](#pipeline-script)
* [Running the Pipeline](#running-the-pipeline)
* [Monitoring Builds](#monitoring-builds)
* [Screenshots & Deliverables](#screenshots--deliverables)
* [What I Learned](#what-i-learned)

---

## Prerequisites

* Jenkins installed and running (locally or on a server)
* Basic knowledge of using a web browser
* User account with permissions to create jobs in Jenkins

---

## Setup Jenkins

1. **Access Jenkins**
   Open your web browser and go to your Jenkins URL (e.g., `http://localhost:8080`).

2. **Login**
   Enter your credentials to log in.

---

## Create a Pipeline Job

1. On the Jenkins dashboard, click **“New Item”**.
2. Enter the item name: `HelloJenkins` (or any name you prefer).
3. Select **“Pipeline”** as the item type.
4. Click **“OK”** to proceed to the job configuration page.

---

## Pipeline Script

1. Scroll down to the **Pipeline** section.

2. In the **Script** box, paste the following Groovy pipeline code:

   ```groovy
   pipeline {
       agent any

       stages {
           stage('Build') {
               steps {
                   echo 'Building the application...'
                   sh 'sleep 5'
               }
           }
           stage('Test') {
               steps {
                   echo 'Running tests...'
                   sh 'sleep 3'
               }
           }
           stage('Deploy') {
               steps {
                   echo 'Deploying the application...'
                   sh 'sleep 2'
               }
           }
           stage('Cleanup') {
               steps {
                   echo 'Cleaning up workspace...'
                   sh 'sleep 1'
               }
           }
       }
       post {
           success {
               echo 'Pipeline executed successfully!'
           }
           failure {
               echo 'Pipeline execution failed!'
           }
       }
   }
   ```

3. (Optional) Check the **“Use Groovy Sandbox”** box.

4. Click **“Save”** at the bottom of the page.

---

## Running the Pipeline

1. After saving, you will be redirected to your new job’s main page.
2. Click the **“Build Now”** button in the left sidebar to trigger a build.
3. You will see a new build appear in the **Build History** panel.

---

## Monitoring Builds

* **View Stage View**:
  On the job page, look for the **Stage View** panel. It shows colored boxes for each stage (Build, Test, Deploy, Cleanup).
* **View Console Output**:
  Click on a build number (e.g., #1) in the Build History, then click **“Console Output”** to view the build logs.

---

## Screenshots & Deliverables

For assignment submission, include the following:

1. **Screenshot of your Jenkins dashboard** with your pipeline job visible.
2. **Screenshot of a successful pipeline execution** (Stage View).
3. **Screenshot of the Console Output** for a completed build.
4. **Brief summary** of what you learned (see below).

---

## What I Learned

> While working on this assignment, I learned how to navigate Jenkins’ dashboard and locate core elements like the jobs list and build history. I successfully created a simple pipeline job that simulates building, testing, deploying, and cleaning up an application using the provided Groovy script. Running the pipeline helped me understand how to monitor builds using both the console log and the visual stage view. Adding a new stage and re-running the build gave me experience in modifying pipelines and seeing immediate feedback in Jenkins. Overall, I gained hands-on familiarity with Jenkins basics and its interface.

---
![image](https://github.com/user-attachments/assets/21994fb9-4558-4f84-bf8c-87cc510f3d90)

![image](https://github.com/user-attachments/assets/c69e74f2-cf0f-4a08-b95d-8f52e43e2d1b)

![image](https://github.com/user-attachments/assets/e121fd26-0ba7-4a36-9343-3326dc707cef)

---

