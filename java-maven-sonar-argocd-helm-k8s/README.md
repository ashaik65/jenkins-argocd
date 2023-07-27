# Jenkins Pipeline for Java based application using Maven, SonarQube, Argo CD, Helm and Kubernetes
Install Helm into EKS cluster

#### Install Helm ####
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh


### Jenkins Install using helm ####$
To deploy jenkins we are using helm chart so we need to add jenkins helm repo and install

helm repo add jenkinsci https://charts.jenkins.io
helm repo update
helm search repo jenkins
helm pull jenkins/jenkins ---> After that do the changes in values.yaml file and install jenkins
tar -xvf jenkins-4.4.2.tgz ----> untar the jenkins tarball to see all the files 

kubectl create ns jenkins

helm install jenkins -f values.yaml .

