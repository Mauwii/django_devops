---
title: ToDo
hide:
 - navigation
---
## :material-notebook-outline: Documentation

- [x] integrate publish_docs into azure-pipelines.yml
- [x] update [workflow chart and Diagrams](../workflow/1-repository.md)
    - [x] update [GitGraph Example](../workflow/1-repository.md#gitgraph-example)
- [ ] Update Documentation (ongoing :see_no_evil:)
- [ ] Build MkDocs for main branch as well, not sure if  this will need mike to work properly or if I can have more Gh-Pages Environments (for free...). Currently I am building MkDocs in main Branch as well, but not publishing it, to make sure it is buildable before allowing a PullRequest to be merged.

## :material-microsoft-azure-devops: Azure-Pipelines

- [ ] Use a naming Convention
    - [ ] maybe even test if it is followed by RegEx
- [x] use variables for default parameters in pipeline-templates
- [ ] Overwrite YAML Triggers for Main pipeline (azure-pipeline.yml) to prevent running it from other Branches (still open since unsure if even necesarry)
- [ ] Add Check to PR-Validation ,before building the WebApp, to see if the Resources already exist, since keys get read out while building the App, which is failing if they don't exist at all
    - [ ] alternative option would be to have those stuff in a keyvault
- [ ] Create branch dependent Variable Templates which could be selected via expressions

## :material-head-lightbulb: Ideas

Since the Human Brain not always works as well as cloud-storage, I will write down some Ideas here. This also has the Advantage that other's could directly correct or improve them, or maybe even take advantage from them as well :smile:

- create a src older and move submodules of mkdocs-material and django_webapp into it
    - search/replace old file path with the new one
