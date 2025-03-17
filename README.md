# Welcome to my genU demo app!

This is a demo Generative AI application built with AWS Bedrock managed by @su3-hokkaido


# System Architecture

The original architecture diagram is managed in [this draw.io file](https://drive.google.com/file/d/1oA3hZ8KquFQ9eNOBPBLKT8VCh-ZCQyuA/view?usp=drive_link) which can be accessed by only @su3-hokkaido.

![System Architecture](./assets/for_markdown/system_architecture_gen_u_bedrock_20250316.png)


# Branch strategy

## Branch naming convention

- `main` is the production branch
- `develop` is the development branch
- `feature/*` is the feature branch
- `hotfix/*` is the hotfix branch

## Branch protection

- `main` and `develop` are protected branches, please ask @su3-hokkaido to approve your PR before merging to these branches.
- Please checkout a new branch from `develop` for your new feature, and merge your PR to `develop`.
- `main` branch is only allowed to be merged from `develop` branch.
- `main` branch is only allowed to be merged by CODEOWNERS.
- `main` branch is automatically deployed to AWS ECR and ECS.

```mermaid
flowchart LR
    develop[develop branch]
    main[main branch]
    feature[feature/* branch]
    hotfix[hotfix/* branch]

    feature -->|Create PR & Ask for CODEOWNERS' approval| develop
    develop -->|CODEOWNERS will merge| main
    hotfix -->|Create PR & Ask for CODEOWNERS' approval| develop
    
    style main fill:#4B0082,stroke:#333
    style develop fill:#00008B,stroke:#333
    style feature fill:#006400,stroke:#333
    style hotfix fill:#DAA520,stroke:#333
```
