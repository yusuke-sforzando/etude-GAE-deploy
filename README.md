# etude-GAE

![Deploy to Google App Engine](https://github.com/yusuke-sforzando/etude-GAE-deploy/workflows/Deploy%20to%20Google%20App%20Engine/badge.svg)
![Python application](https://github.com/yusuke-sforzando/etude-GAE-deploy/workflows/Python%20application/badge.svg)
Practice for automatic GAE deployments on GitHub Actions.  
Deploy to [q-lako](https://q-lako.appspot.com)

- [etude-GAE](#etude-gae)
  - [Requirements](#requirements)
  - [How to Run](#how-to-run)
    - [Create Virtual Environment](#create-virtual-environment)
    - [Run](#run)
    - [Lint](#lint)
    - [Test](#test)
    - [Install Python Packages](#install-python-packages)
    - [Install Node.js Packages](#install-nodejs-packages)
    - [Google Cloud SDK for GAE/Python (If you want to deploy to GAE in a local environment.)](#google-cloud-sdk-for-gaepython-if-you-want-to-deploy-to-gae-in-a-local-environment)
      - [Case of MacOS w/ Homebrew](#case-of-macos-w-homebrew)
      - [Case of others](#case-of-others)

## Requirements

- Python 3.8.5 or higher
  - [pytest](https://docs.pytest.org/en/stable/)
    - [pytest-cov](https://pypi.org/project/pytest-cov/)
  - [flake8](https://pypi.org/project/flake8/)
  - [Google Cloud SDK](https://cloud.google.com/sdk/)(If you want to deploy to GAE in a local environment.)
  - [Flask](http://flask.pocoo.org/)
- Node.js
  - [npm](https://www.npmjs.com)
  - [Vue.js](https://jp.vuejs.org/index.html)

## How to Run

In your local environment, follow the steps below to set up your environment.

### Create Virtual Environment

```shell
python3 -m venv venv
source venv/bin/activate
```

### Run

Launch flask and start up the server.

```shell
python main.py
```

### Lint

Check the code according to PEP8.

```shell
flake8 *.py
```

### Test

Test the python code to make sure it is behaving as expected.
In addition, measure the coverage of the test code.

```shell
python -m pytest -vv . --capture=no --cov --cov-report=xml
```

### Install Python Packages

Upgrade the python module.

```shell
pip install -t lib -r python-requirements.txt --upgrade
```

### Install Node.js Packages

```shell
npm install
```

### Google Cloud SDK for GAE/Python (If you want to deploy to GAE in a local environment.)

#### Case of MacOS w/ Homebrew

```shell
brew cask install google-cloud-sdk
gcloud components install app-engine-python
```

#### Case of others

Download SDK from [official site](https://cloud.google.com/sdk/) and install it.
