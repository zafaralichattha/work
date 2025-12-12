# This is a basic workflow to help you get started with Actions
name: Simple Manual Workflow - Three Env

# Controls when the action will run
on:
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  DEV:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest
    environment: Development

    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v2
      - name: Run a script
        run: |
          echo "I am running a job in the DEV environment"

  QA:
    runs-on: ubuntu-latest
    environment: Staging
    needs: DEV

    steps:
      - uses: actions/checkout@v2
      - name: Run a script
        run: |
          echo "I am running a job in the QA environment"

  PROD:
    runs-on: ubuntu-latest
    environment: Production
    needs: QA

    steps:
      - uses: actions/checkout@v2
      - name: Run a script
        run: |
          echo "I am running a job in the PROD environment"
