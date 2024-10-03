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

Launch the mlflow server

```bash
$ mlflow server --host 127.0.0.1 --port 8080
```

You can access the mlflow UI at [http://localhost:8080](http://localhost:8080)

Train a model

```bash
$ poetry run python scripts/train.py
```

Now you can access the mlflow UI and see the model you just trained with name 'MLflow Quick Start'
