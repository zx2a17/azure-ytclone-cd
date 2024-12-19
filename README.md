# Build and Deploy a Modern YouTube Clone Application in React JS with Material UI 5

## This is a code repo that takes the code of the app and deploy onto Azure to demostrate the CD capability on azure using the Azure DevOps Pipeline

Following high level steps are used to achieve an deployment to the Azure resources.

This depicts the connection between the pipeline where the code resides and the compute resources in az portal

``` mermaid
graph LR
A[Azure Pipeline] <--> |Authentication| B[Azure Portal]

```

1) Download code base from github to local
2) push the local code onto ADO (Azure DevOps)
3) Create App Service on AP (azure Portal) - this example is a react app, so using node 18 LTS as runtime stack
4) Create pipeline on ADO using the source code pushed in step 2

   a) Classic Editor will use the following steps
   - npm install
   - npm build
   - Publish Artifact (path to publish already takes into account your code repo, therefore only putting "build" here as the path)
   - Azure App service deploy
   
   b) Azure Repos Git
    - select azure-pipelines.yml that exist on the repo, already have the steps defined

5) run the jobs and check for any errors!
6) note that in this example I needed to use a self hosted runner (agent) documentation can be found here:

   configure the agent via ADO under organisation settings and Agent Pool

   https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/agents?view=azure-devops&tabs=yaml%2Cbrowser







reference tutorial
https://www.youtube.com/watch?v=3Nv-FzzrqYU&list=PLl4APkPHzsUXseJO1a03CtfRDzr2hivbD&index=5
