---
title: Done
icon: material/checkbox-outline
---
## :material-checkbox-outline: Done

### PR-Source-Validation to prevent Secret-Leakage

- [x] Make Separate Pipelines for Pull-Request Validation
    - [x] also check if it is running from correct branch, otherwise fail
    - [x] checkout corresponding Branch from where the Check should be done before verification is done, otherwise easy hackable

Not necesarry after finding out that PullRequests from other Repositorys will not be able to use Secrets. Also Configured that first Timers always need confirmation, so for now I think it is fine.

### gitGraph Update

- [x] update [GitGraph Example](https://mauwii.github.io/django_devops/todo/#gitgraph-example)
