# Deploying a NodeJS docker image to beta and production Kubernetes cluster with your Shippable pipeline.

![AyeAye](https://github.com/devops-recipes/deploy-kubernetes-basic/raw/master/public/resources/images/captain.png)

This repository demonstrates the following :
- Setup CI for a NodeJS application that builds a docker image and deploys it to DockerHub.
- Setup a CD pipeline to deploy the NodeJS docker image to beta and production
Kubernetes clusters.

## Prerequisites to run this sample

* Source control account (e.g. GitHub, Bitbucket, Gitlab)
* Shippable account (sign up for free at www.shippable.com)
* Kubernetes cluster.

## Setup
* Fork this repo into your local repository in your source control account.
* Login into Shippable with your source control account(wwww.shippable.com).
* Create a [Docker Registry integration](http://docs.shippable.com/platform/integration/dockerRegistryLogin/) on shippable to your docker hub.
* All your CI configuration is in `shippable.yml` file, while you will modify next to reflect your integration.
* Update the integrationName in the integration.hub section with the integration name created above.
* Change the DOCKER_REPO and DOCKER_ACC to point to your repo and docker account.
* Next, follow these [CI Setup Instructions](http://docs.shippable.com/ci/runFirstBuild/) to enable your forked project for CI.
* Build your CI project by clicking on the build button. Once the build completes, the NodeJS docker image will be pushed to your DockerHub account.
* Create the Kubernetes integrations for beta and production environments using instructions provided [here](http://docs.shippable.com/platform/integration/kubernetes-config/).

## Add the pipeline  in Shippable
* Sign in with your shippable account, select your subscription from the dropdown menu in upper left (three horizontal lines).
* Select the Pipelines tab.
* Select the "+" icon in the upper right.
* Select the source control repo where your fork is. This will render all the jobs in the Single pane of glass (SPOG).
* Run the pipeline following instructions [here]().

## CI Console Output
![CI Console Output](https://github.com/devops-recipes/deploy-kubernetes-multi-env/raw/master/public/resources/images/console.png)

##Build link
[CI build on Shippable](https://app.shippable.com/github/devops-recipes/deploy-kubernetes-multi-env/runs/12/1/console)

##Build status badge
[![Run Status](https://api.shippable.com/projects/58ff7b2e28b7f006008c7b72/badge?branch=master
)](https://app.shippable.com/github/devops-recipes/deploy-kubernetes-multi-env)

## Pipeline View
![Pipeline](https://github.com/devops-recipes/deploy-kubernetes-multi-env/raw/master/public/resources/images/dkme-pipeline-view.png)

## Deploy job View
![Beta Deploy1](https://github.com/devops-recipes/deploy-kubernetes-multi-env/raw/master/public/resources/images/dkme-beta-deploy-view.png)
![Prod Deploy2](https://github.com/devops-recipes/deploy-kubernetes-multi-env/raw/master/public/resources/images/dkme-prod-deploy-view.png)
![Blue Deploy](https://github.com/devops-recipes/deploy-kubernetes-multi-env/raw/master/public/resources/images/dkme-blue-deploy-view.png)
![Green Deploy](https://github.com/devops-recipes/deploy-kubernetes-multi-env/raw/master/public/resources/images/dkme-green-deploy-view.png)
