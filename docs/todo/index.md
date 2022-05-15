---
title: ToDo
hide:
 - navigation
---
## :material-notebook-outline: Documentation

- [x] Update Documentation (ongoing :see_no_evil:)
- [x] integrate publish_docs into azure-pipelines.yml
- [x] update [workflow chart and Diagrams](../workflow/1-repository.md)
    - [x] update [commit flow example](../workflow/1-repository.md#commit-flow-example)
- [ ] Build MkDocs for main branch as well as stable branch, not sure if this will need the mkdocs-plugin `mike` to work properly or if I can have more Environments in GitHub-Pages (for free...).<br>Currently I am building MkDocs in main Branch as well, but not publishing it, to make sure it is buildable before allowing a PullRequest to be merged.

## :material-microsoft-azure-devops: Azure-Pipelines

- [x] use variables for default parameters in pipeline-templates
- [ ] Use a naming Convention
    - [ ] maybe even test if it is followed by RegEx
- [ ] update bicep template and add a KeyVault to store:
    - [ ] Application Insights
        - [ ] Secret
        - [ ] Connection String
- [ ] Create branch dependent Variable Templates (done for main)
    - [ ] select correct template by destination branch

Maybe unnecessary

- [ ] Overwrite YAML Triggers for Main pipeline (azure-pipeline.yml) to prevent running it from other Branches (still open since unsure if even necesarry)
- [ ] Add Check to PR-Validation ,before building the WebApp, to see if the Resources already exist, since keys get read out while building the App, which is failing if they don't exist at all

## :material-head-lightbulb: Ideas

Since the Human Brain not always works as well as cloud-storage, I will write down some Ideas here. This also has the Advantage that other's could directly correct or improve them, or maybe even take advantage from them as well :smile:

- [x] create a src older and move submodules of mkdocs-material and django_webapp into it
    - [x] search/replace old file path with the new one
- [ ] auto-complete pull requests
    - [ ] maybe based on [tags](https://docs.microsoft.com/en-us/azure/devops/pipelines/repos/github?view=azure-devops&tabs=yaml#label-sources)
