---
title: Ideas
icon: material-lightbulb-on
---

Since the Human Brain not always works as well as cloud-storage, I will write down some Ideas here. This also has the Advantage that other's could directly correct or improve them, or maybe even take advantage from them as well :smile:

- add a comparing check to validate_pr to compare if a pipeline yaml has changed and fail if was changed but allow changes by owner
  - files to check:
    - azure-pipelines.yml
    - azure-pipelines/validate_pr.yml
    - .vscode/*
- integrate publish_docs into azure-pipelines.yml
- create a src older and move submodules of mkdocs-material and django_webapp into it
  - search/replace old file path with the new one
