Here is a quickstart guide for using GitHub Actions:

## What are GitHub Actions?

GitHub Actions is a powerful automation tool that allows you to build, test, and deploy your code directly from GitHub. It enables you to create custom workflows based on different events in your repository like new pull requests, issues, releases, etc. [1]

## Setting Up Your First Workflow

To get started with GitHub Actions, you need to create a YAML file in the `.github/workflows` directory of your repository. This file will define the steps and actions that make up your workflow.

1. **Create the workflow file**: In your repository, create the `.github/workflows` directory if it doesn't exist, and add a new file with a descriptive name like `ci.yml`.

2. **Define the workflow**: Open the `ci.yml` file and define your workflow by specifying the events that should trigger it. For example, to run the workflow on every push to the `main` branch:

```yaml
name: CI

on:
  push:
    branches: [ main ]

jobs:

  build:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v3
    - name: Run a script
      run: echo "Hello, GitHub Actions!"
```

This basic workflow has a single job called `build` that runs on the latest Ubuntu virtual machine. The job has two steps: one that checks out the repository code, and another that runs a simple script. [2]

3. **Commit the file**: Commit the `ci.yml` file to your repository's `main` branch. This will trigger the new workflow you just created.

4. **View the workflow run**: On GitHub, navigate to the `Actions` tab of your repository to see the workflow run and its logs.

## Next Steps

This was just a simple example to get you started. GitHub Actions supports a wide range of tools and programming languages, allowing you to build complex workflows for continuous integration, deployment, code analysis, and more.

Some useful next steps:

- Explore the GitHub Actions Marketplace to find pre-built actions to include in your workflows[3]
- Learn how to create custom actions and share them with others[2]
- Check out examples and guides for common use cases like deploying to cloud providers, publishing packages, and more[4]
- Automate your entire software development lifecycle with GitHub Actions[1]

With GitHub Actions, you can streamline your development processes and ensure consistent, reliable builds and deployments directly from your GitHub repository. [1][2][3][4]

Citations:
[1] https://www.learnenough.com/blog/git-actions-tutorial
[2] https://docs.github.com/en/actions/learn-github-actions
[3] https://everhour.com/blog/github-actions-tutorial/
[4] https://docs.github.com/en/actions/quickstart
[5] https://codefresh.io/learn/github-actions/github-actions-tutorial-and-examples/
[6] https://docs.github.com/en/actions
[7] https://www.youtube.com/watch?v=ylEy4eLdhFs
[8] https://github.com/osohq/oso-go-quickstart/actions
