# OpenShift CI/CD Final Project

A small Flask application for GitHub Actions CI and OpenShift/Tekton.

## Run locally
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt -r requirements-dev.txt
python app.py
```
Visit `/` and `/health` on port 8080.

## CI
`.github/workflows/workflow.yml` runs Flake8 and nose on push and pull request.

## Tekton
`.tekton/tasks.yml` contains the `nose-test` and `cleanup` tasks. `.tekton/pipeline.yml` defines a pipeline that clones the repository, runs tests, then cleanup. The pipeline expects the cluster's `git-clone` Task to be installed.

## OpenShift
Apply resources from `openshift/` in a project where you have permissions. The deployment is a starter example and should be adapted to use your built application image for production.

## Evidence required by the assignment
Capture real screenshots of PVC details, pipeline details, successful PipelineRun, and application logs from your OpenShift environment. These cannot be fabricated in this repository.
