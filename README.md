# Image Classification using AWS SageMaker

The purpose of this project is to create a dog breed image classifier. I did this by creating a neural net using resnet50 as a base. There are 133 dog breeds which are the final classes with 500+ dog images.

## Project Set Up and Installation
First we had to install basic dependencies (smdebug)
Second I had to download and unzip the dog images into their own directories.
Third I had to make a tuner with hyper parameter ranges and fit it.
Fourth I took the best hps and ran a training script with them for longer with profiling and debugging.
Fifth I generated reports and made plots to see utilization for optimization.
Sixth I deployed the model to an endpoint and queried it.


## Dataset
The provided dataset is a dogbreed classification dataset.
The images are each placed in their respective breed folder.

### Access
The dataset was uploaded to an s3 bucket. 

## Hyperparameter Tuning
The model was a nueral net Image Classifier because its designed to classify Images. I used learning rate, batch-size, and epochs
"lr": ContinuousParameter(0.001, 0.1),"batch-size": CategoricalParameter([32, 64, 128, 256, 512]),"epochs": IntegerParameter(2, 4)


Screenshot of training jobs:
![alt text](https://github.com/jjput1/DogNN/blob/main/Screenshot_training_jobs.PNG)

## Files used
The train_and_deploy.ipynb file is the step by step notebook
hpo.py is the tuner script.
train_model.py is the final training script.

## Debugging and Profiling

I put in hooks for debugging and profiling. Also I put in logging statements on each step so I could monitor cloud watch. I was able to see that it wasn't working with these and then make code changes to fix the issue. 


### Results

I used the debbugger to make a plot of the cross entropy loss over time. The profiler showed that I wasn't taxing the cpu.



## Model Deployment
I deployed the model with a simple estimator.deploy() call. It crashed however when querying it.

Screenshot of deployed endpoint:
![alt text](https://github.com/jjput1/DogNN/blob/main/screenshot_endpoint.PNG)

## Standout Suggestions

