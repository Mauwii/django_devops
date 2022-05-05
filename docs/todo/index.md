---
title: ToDo
icon: material/tooltip-edit-outline
hide:
  - navigation
---

Integrate better Branching Strategy:
  
|     instance     | Branch name            |              Protected Branch               | Create From         |
| :--------------: | :--------------------- | :-----------------------------------------: | :------------------ |
| feature-branches | feature/* <br> issue/* |                      -                      | from Head of main   |
|  working branch  | main                   | only from feature/* <br> issue/* and hotfix | Pull-Request only   |
|      hotfix      | hotfix/*               |                      -                      | from Head of stable |
|     release      | stable                 |           only by main and hotfix           | Pull-Request only   |

Main branch is used as the working branch. To develope new features, create branch from main branch called `feature/<jira-id>-<feature-name>` for new features, or `issue/<jira-id>` when solving a issue. When development of the feature or issue is done, merge it back into the main branch with a pull request.

When time has come for a release, create a pull request to merge main into stable.

For bigger problems, like f.E. a zero-day, create a branch from stable and name it `hotfix/<jira-id>` and try to fix the issue asap. When done, merge this hotfix back into stable as well as into main.

### Flowchart

```` mermaid
  graph LR
    dev --> main;
    main -.-> dev;
    main --> stable;
    stable -.-> hotfix;
    hotfix --> stable & main;
````

### GitGraph example

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
        checkout feature-2
        commit
        checkout stable
        branch hotfix-1
        commit
        commit
        checkout main
        merge hotfix-1
        checkout stable
        merge hotfix-1
        checkout stable
        commit tag: "v1-hotfix"
        checkout feature-2
        commit
        checkout main
        merge feature-2
        checkout stable
        merge main
        commit tag: "v2"
```

### Automation

Of course the approach is to have as much automated as possible, which also means that pull-request should in the end get tested and resolved by themselves (...or the help of Azure-Pipelines :material-microsoft-azure-devops:)
