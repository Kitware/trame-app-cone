# Cloud deployment example

This repository provide a simple example on how to deploy a single file trame application onto a CapRover instance using the git approach.

## Background

When creating a single file application with trame the only files that you need to edit for your specific needs are:
- `app.py`: Should contain your own application code with a `__main__` section
- `./setup/requirements.txt`: Should list all your dependencies including `trame`
- `./setup/apps.yaml`: Should add any additional args/parameters you may need for your app. Or list all the app you want to deploy at once.

Generic file that don't needs edits:
- `Dockerfile`: contains the basic multi-user setup for trame apps.
- `captain-definition` Point to the dockerfile for building the deployment.

## CapRover endpoint setup

Within the CapRover web interface, for your application make sure you enable `"WebSocket Support"` at the bottom of the `"HTTP Settings"` page. 

Then ideally you should also __Enable HTTPS__ and check __Force HTTPS by redirecting all HTTP traffic to HTTPS__

## How to deploy

The idea is to rely directly on git so in order to deploy such repository, you should be able to run the following command lines:

```bash
git clone https://github.com/Kitware/trame-app-cone.git
cd trame-app-cone.git
caprover deploy
```

