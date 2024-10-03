## Requirements

- pyenv
- poetry

## Installation

```bash
$ pyenv install 3.12.2
$ pyenv local 3.12.2
$ poetry shell
$ poetry install
```

## Usage

### Simple Training

[see the official documentation](https://mlflow.org/docs/latest/getting-started/intro-quickstart/index.html)

````bash
Launch the mlflow server

```bash
$ mlflow server --host 127.0.0.1 --port 8080
````

You can access the mlflow UI at [http://localhost:8080](http://localhost:8080)

Train a model

```bash
$ poetry run python scripts/train.py
```

Now you can access the mlflow UI and see the model you just trained with name 'MLflow Quick Start'

### Compare runs, choose a model, and deploy it to a REST API

[see the official documentation](https://mlflow.org/docs/latest/getting-started/quickstart-2/index.html)

```bash
$ poetry run python scripts/compare_runs.py
```

You can choose the best model and deploy it to a REST API at [http://localhost:8080](http://localhost:8080)

After you deploy the model, you can test it with the following command:

```bash
curl -d '{"dataframe_split": {
"columns": ["fixed acidity","volatile acidity","citric acid","residual sugar","chlorides","free sulfur dioxide","total sulfur dioxide","density","pH","sulphates","alcohol"],
"data": [[7,0.27,0.36,20.7,0.045,45,170,1.001,3,0.45,8.8]]}}' \
-H 'Content-Type: application/json' -X POST localhost:5002/invocations
```
