Example taken from https://github.com/mlflow/mlflow/tree/master/examples/tensorflow/tf2

Setup
Create a code with url- https://github.com/oneconvergence/dkubeio-examples/tree/mlflow/mlflow branch -mlflow
Create an output model
Traning
Create a vs code IDE with tensorflow 2.6.0 cpu image
cd to the code directory where we have the conda.yaml file
conda env create -f conda.yaml
conda activate tensorflow-example
python train_predict.py --code {code name} --output {output model name}
Building Image
Go to the model details page which was given as output in the above training run. A new version will be there in the version list.
Click on the build model image icon which is on the version's row at the right.
Select code
Select registry
Submit to create image build
Deployment
Select serving image which was build in the previous step.
Serving Port: 8000
Serving Url Prefix: /invocations
Min CPU/Max CPU: 1
Min Memory/Max Memory: 5G
Prediction
Copy the curl command from the deployment page
Change the data section to -d '{ "columns": ["SepalLength", "SepalWidth", "PetalLength", "PetalWidth"], "data": [[5.1, 3.3, 1.7, 0.5], [5.9, 3.0, 4.2, 1.5], [6.9, 3.1, 5.4, 2.1]] }'
