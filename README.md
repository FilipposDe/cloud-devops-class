Basic CI/CD pipeline with Jenkins, Ansible and Minikube. On update, Ansible applies `deployment.yml` which is set up for rolling update.

#### Requirements
* Jenkins (root user, docker plugin)
* Ansible (needs python, openshift for k8s module)
* Docker
* Kubectl
* Minikube

#### Steps
1. Fork this repo
2. Set your Docker Hub credentials in Jenkins as docker_id
3. In `Jenkinsfile` and `deployment.yml`, replace `philipposde/udacity2` with your registry path
4. Add pipeline to Jenkins, from your GitHub repo

The app serves a basic html webpage.
