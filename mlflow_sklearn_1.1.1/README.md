Example taken from https://github.com/mlflow/mlflow/tree/master/examples/sklearn_elasticnet_wine

### Setup
1. Create a code with url- https://github.com/kparimalla/mlflow/tree/main/mlflow_sklearn_1.1.1 and branch as main
2. Create an output model 

### Traning
1. Create a vs code IDE with sklearn 1.1.1 cpu image
2. cd to the code directory where we have the conda.yaml file
3. conda env create -f conda.yaml
4. conda activate mlflow_sklearn
5. python train.py --code {code name} --output {output model name}

### Building Image
1. Go to the model details page which was given as output in the above training run. A new version will be there in the version list.
2. Click on the build model image icon which is on the version's row at the right.
3. Select code
4. Select registry
5. Submit to create image build

### Deployment
1. Select serving image which was build in the previous step.
2. Serving Port: 8000
3. Serving Url Prefix: /invocations
4. Min CPU/Max CPU: 1
5. Min Memory/Max Memory: 5G

### Prediction
1. Copy the curl command from the deployment page
2. Change the Content-Type & data section to,
"Content-Type: text/csv" --data-binary "@wine-quality.csv"

