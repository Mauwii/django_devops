---
title: ToDo
---

- [ ] Overwrite YAML Triggers for PR-Validation to prevent running them from other Branches
- [ ] Add Check in PR-Validation before building the WebApp, to see if the Resources already exist, since keys get read out while building the App, which is failing if they don't exist at all
- [ ] Update Documentation
    - [x] update [GitGraph Example](https://mauwii.github.io/django_devops/todo/#gitgraph-example)
    - [ ] update Workflow

maybe not necessary anymore after Idea to prevent problems at PR-Validation with overwriting yaml triggers in Azure-Pipelines

- [ ] Make Separate Pipelines for Pull-Request Validation
    - [ ] also check if it is running from correct branch, otherwise fail
    - [ ] checkout corresponding Branch from where the Check should be done before verification is done, otherwise easy hackable
