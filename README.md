# Example of workflow to deploy react to s3


```
name: Upload Website

# This file was made by lord of the cat - meow 
on:
  push:
    branches:
    - main
  workflow_dispatch: 
    inputs: 
     envFile:
      description: Env file to deploy
      type: string
      required: false
      default: '.env.production'

jobs:
  DeployToAWS: 
     uses: meowmeoworg/workflow-support/.github/workflows/DeployReactStaticWebToS3.yml@develop
     with:
      envFile: ${{inputs.envFile}}
     secrets:
      AWS_S3_BUCKET: ${{ secrets.AWS_S3_BUCKET }}
      AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
      AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
    
```
