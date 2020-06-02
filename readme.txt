Basic CI/CD pipeline with Jenkins, Ansible and Minikube

Requirements
Installed:
Jenkins (with sudo privileges)
Ansible
Docker
Kubectl
Minikube

Steps
Fork this repo
Set your Docker Hub credentials in Jenkins
In Jenkinsfile and deployment.yml, replace philipposde/udacity2 with your registry path
Add pipeline to Jenkins, from your GitHub repository

The app serves a basic html webpage.






curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x minikube
sudo mkdir -p /usr/local/bin/
sudo install minikube /usr/local/bin/
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
sudo pip install --upgrade --user openshift
minikube start --driver=docker

