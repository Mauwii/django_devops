---
title: Open
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
