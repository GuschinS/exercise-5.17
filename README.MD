# Inspect available vagrant boxes 
vagrant status 

# create a vagrant box using the Vagrantfile in the current directory
vagrant up

# SSH into the vagrant box
# Note: this command uses the .vagrant folder to identify the details of the vagrant box
vagrant ssh

sudo su

vagrant destroy
vagrant suspend
vagrant halt
vagrant provision


# K3S
curl -sfL https://get.k3s.io | INSTALL_K3S_VERSION=v1.20.8-rc1+k3s1 sh

# ArgoCD

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml


kubectl get po -n argocd

kubectl get svc -n argocd

# service/argocd-server-nodeport created

kubectl apply -n argocd -f https://raw.githubusercontent.com/udacity/nd064_course_1/main/solutions/argocd/argocd-server-nodeport.yaml

kubectl get svc -n argocd argocd-server -o yaml  

# password

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

EWRXBktUSPIKoQwT

# nginx-staging created

kubectl apply -f https://raw.githubusercontent.com/GuschinS/exercise-5.17/master/nginx-deployment/argocd-helm-nginx-staging.yaml

# nginx-prod created

kubectl apply -f https://raw.githubusercontent.com/GuschinS/exercise-5.17/master/nginx-deployment/argocd-helm-nginx-prod.yaml

