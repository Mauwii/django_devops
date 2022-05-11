---
title: Repository
theme:
  icon:
    logo: material/notebook-outline
---

In this Section you will find Informations related to the Repository, like a

### Branching Strategy

#### Table

|     instance     | Branch name            |          accept PR from           | Create From    | other infos                                                                                                                |
| :--------------: | :--------------------- | :-------------------------------: | :------------- | :------------------------------------------------------------------------------------------------------------------------- |
| feature-branches | feature/\*<br>issue/\* |               main                | Head of main   | must be up to date with main for PR                                                                                        |
|  working branch  | main                   | feature/\* <br>issue/\*<br>hotfix | Pull-Request   | Require linear history<br>Require status checks to pass before merging<br>Require branches to be up to date before merging |
|      hotfix      | hotfix/*               |                 -                 | Head of stable |
|     release      | stable                 |          main<br>hotfix           | Pull-Request   |

Main branch is used as the working branch. To develope new features, create branch from main branch called `feature/<jira-id>-<feature-name>` for new features, or `issue/<jira-id>` when solving a issue. When development of the feature or issue is done, merge it back into the main branch with a pull request.

When time has come for a release, create a pull request to merge main into stable.

For bigger problems, like f.E. a zero-day, create a branch from stable and name it `hotfix/<jira-id>` and try to fix the issue asap. When done, merge this hotfix back into stable as well as into main.

#### Diagram

##### Small

````mermaid
graph LR
    dev --> main;
    main -.-> dev;
    main --> stable;
    stable -.-> hotfix;
    hotfix --> stable & main;
````

##### Detailed

```mermaid
graph LR
  Code[(Code)] -- Commit<br>Changes --> FeatureBranch[Feature<br>Branch];
  FeatureBranch[Feature<br>Branch] -- Pull<br>Request --> MainBranch[Main<br>Branch];
  MainBranch -- Trigger<br>Build --> CheckFeature{Built<br>succesfull};
  CheckFeature -- Yes --> CompleteMerge[/Complete Merge/];
  CompleteMerge -- Trigger<br>Build --> CheckMain{Built<br>succesfull};
  CheckMain -- Yes --> DeployMain[/Deploy<br>Main Branch/];
  DeployMain --> DeleteFeature[\Delete<br>Feature Branch\];
  CheckMain -- No --> RevertMerge[\Revert Merge\];
  RevertMerge[\Revert Merge\] --> TryBugFix{try to<br>fix bugs};
  TryBugFix -- No --> DeleteFeature;
  CheckFeature -- No --> TryBugFix;
  TryBugFix -- yes --> Code;
```

A more detailed Workflow-Diagram is located in the next

#### GitGraph example

``` mermaid
    gitGraph
        commit
        branch stable
        checkout stable
        commit tag: "v1"
        checkout main
        branch feature-1
        checkout feature-1
        commit
        commit
        checkout main
        branch feature-2
        checkout feature-2
        commit
        checkout main
        merge feature-1
        commit
        checkout feature-2
        commit
        checkout stable
        branch hotfix-1
        commit
        commit
        checkout main
        merge hotfix-1
        commit
        checkout stable
        merge hotfix-1
        commit tag: "v1-hotfix"
        checkout feature-2
        commit
        merge main
        checkout main
        merge feature-2
        commit
        checkout stable
        merge main
        commit tag: "v2"
```

#### Automation

Of course the approach is to have as much automated as possible, which also means that pull-request should in the end get tested and resolved by themselves (...or the help of Azure-Pipelines :material-microsoft-azure-devops:)
