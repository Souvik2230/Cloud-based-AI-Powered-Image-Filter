Cloud Based AI powered image filter

Use AWS Sagemaker to train a pretrained model that can perform image classification by using the Sagemaker profiling, debugger, hyperparameter tuning and other good ML engineering practices. This can be done on either the provided dog breed classication data set or one of your choice.

Project Set Up and Installation

The provided dataset is the dogbreed classification dataset which can be found in the classroom. The project is designed to be dataset independent so if there is a dataset that is more interesting or relevant to your work, you are welcome to use it to complete the project.

Dataset

The provided dataset is the dogbreed classification dataset which can be found in the classroom. The project is designed to be dataset independent so if there is a dataset that is more interesting or relevant to your work, you are welcome to use it to complete the project.

Access

Upload the data to an S3 bucket through the AWS Gateway so that SageMaker has access to the data.

Hyperparameter Tuning

In this experiment, we used the ResNet50 model to perform image classification. We performed hyperparameter search, using the hpo.py script, to find the optimal values for the learning rate and batch size. The learning rate was searched over a continuous range from 0.001 to 0.1, while the batch size was searched over a categorical set of values including 16, 32, 64, 128, 256, and 512.Finally, we used the best values for the learning rate and batch size to train the model for 20 epochs. https://github.com/Souvik2230/Cloud-based-AI-Powered-Image-Filter/blob/ede2fc2b068274a2aeb7be4b410f572644b43e21/hpo.png

Training

The model was then trained using the train.py script. The model was trained for 20 epochs and completed with an accuracy of about 81% (which needs improvement :/ ) https://github.com/Souvik2230/Cloud-based-AI-Powered-Image-Filter/blob/65a83fa787aaf3d54aacff183dfc00d67bcd061f/train.png

Debugging

Model debugging in sagemaker is done using the smdebug library which is a part of the sagemaker python sdk. The library provides a set of hooks that can be used to capture the values of tensors at different points in the training process. The library also provides a set of rules that can be used to detect

Profiling

Using Sagemaker Profiler, we monitored Instance metrics, GPU/CPU utilization and GPU/CPU memory utilization.
To use Sagemaker Profiler we created profiler rules and configurations. The output is a HTML report.

Results

The profiler report revealed that the model trained for about 40 minutes.
It also revealed that the model was underutilising the GPU.
