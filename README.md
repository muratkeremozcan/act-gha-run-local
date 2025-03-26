# Overview

Simple Node.js application to demonstrate the use of [act](https://github.com/nektos/act)

```bash
brew install act
# OR using the installation script
curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/nektos/act/master/install.sh | sudo bash
```

Start Docker.

```bash
# Basic run (will execute the push workflow)
act
# For Mac M*, append --container-architecture linux/amd64
act --container-architecture linux/amd64

# List available workflows and jobs
act -l  --container-architecture linux/amd64

# RECOMMENDED: Run a specific job in a specific workflow
act -j my-job -W .github/workflows/my-workflow.yml --container-architecture linux/amd64

# Run the full workflow
act -W .github/workflows/my-workflow.yml --container-architecture linux/amd64

# additional options

# Use a custom GitHub token if needed
act -s GITHUB_TOKEN=your_token

# Run with verbose output for debugging
act -v

```

## What Happens Behind the Scenes

1. Act reads your workflow file
2. Pulls necessary Docker images to simulate GitHub's runner environment
3. Creates isolated containers to run each job
4. Executes the steps defined in your workflow
5. Shows you the output directly in your terminal
