---
title: ToDo
---

## :material-notebook-outline: Documentation

- [ ] Update Documentation (ongoing :see_no_evil:)
- [ ] Build MkDocs for main branch as well, not sure if  this will need mike to work properly or if I can have more Gh-Pages Environments (4 free...)<br>Currently I am building MkDocs in main Branch as well, but not publishing it yet.

## :material-microsoft-azure-devops: Azure-Pipelines

- [ ] Use a naming Convention
    - [ ] maybe even test if it is followed by RegEx
- [ ] use variables for default parameters in pipeline-templates<br>right
- [ ] Overwrite YAML Triggers for Main pipeline (azure-pipeline.yml) to prevent running it from other Branches
- [ ] update Workflow Chart
- [ ] Add Check to PR-Validation ,before building the WebApp, to see if the Resources already exist, since keys get read out while building the App, which is failing if they don't exist at all
    - [ ] alternative option would be to have those stuff in a keyvault
- [ ] Create branch dependent Variable Templates which could be selected via expressions

## :material-checkbox-outline: Done

### PR-Source-Validation to prevent Secret-Leakage

- [x] Make Separate Pipelines for Pull-Request Validation
    - [x] also check if it is running from correct branch, otherwise fail
    - [x] checkout corresponding Branch from where the Check should be done before verification is done, otherwise easy hackable

Not necesarry after finding out that PullRequests from other Repositorys will not be able to use Secrets. Also Configured that first Timers always need confirmation, so for now I think it is fine.

### gitGraph Update

- [x] update [GitGraph Example](https://mauwii.github.io/django_devops/todo/#gitgraph-example)

## :material-head-lightbulb: Ideas

Since the Human Brain not always works as well as cloud-storage, I will write down some Ideas here. This also has the Advantage that other's could directly correct or improve them, or maybe even take advantage from them as well :smile:

- [x] integrate publish_docs into azure-pipelines.yml
- create a src older and move submodules of mkdocs-material and django_webapp into it
    - search/replace old file path with the new one
