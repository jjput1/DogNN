# Image Classification using AWS SageMaker

Use AWS Sagemaker to train a pretrained model that can perform image classification by using the Sagemaker profiling, debugger, hyperparameter tuning and other good ML engineering practices. This can be done on either the provided dog breed classication data set or one of your choice.

## Project Set Up and Installation
Enter AWS through the gateway in the course and open SageMaker Studio. 
Download the starter files.
Download/Make the dataset available. 

## Dataset
The provided dataset is the dogbreed classification dataset which can be found in the classroom.
The project is designed to be dataset independent so if there is a dataset that is more interesting or relevant to your work, you are welcome to use it to complete the project.

### Access
Upload the data to an S3 bucket through the AWS Gateway so that SageMaker has access to the data. 

## Hyperparameter Tuning
What kind of model did you choose for this experiment and why? Give an overview of the types of parameters and their ranges used for the hyperparameter search

It was a nueral net Image Classifier because its designed to classify Images. I used learning rate, batch-size, and epochs
"lr": ContinuousParameter(0.001, 0.1),"batch-size": CategoricalParameter([32, 64, 128, 256, 512]),"epochs": IntegerParameter(2, 4)

Remember that your README should:
- Include a screenshot of completed training jobs
- Logs metrics during the training process
- Tune at least two hyperparameters
- Retrieve the best best hyperparameters from all your training jobs

## Debugging and Profiling

I put in hooks for debugging and profiling. Also I put in logging statements on each step so I could monitor cloud watch. I was able to see that it wasn't working with these and then make code changes to fix the issue. 


### Results

I used the debbugger to make a plot of the cross entropy loss over time. The profiler showed that I wasn't taxing the cpu.



## Model Deployment
**TODO**: Give an overview of the deployed model and instructions on how to query the endpoint with a sample input.
I deployed it with a simple estimator.deploy() call. It crashed however when querying it.
**TODO** Remember to provide a screenshot of the deployed active endpoint in Sagemaker.

## Standout Suggestions
**TODO (Optional):** This is where you can provide information about any standout suggestions that you have attempted.
