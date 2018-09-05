# Minikube

## Installation

### Installation Process

```bash
# Install Kubectl on PS:
choco install kubernetes-cli

# Install Minikube by downloading and renaming
wget https://storage.googleapis.com/minikube/releases/latest/minikube-windows-amd64.exe && mv minikube-windows-amd64.exe minikube.exe

# I needed to create the ExternalSwitch

# Because of my setup, the following was run in a powershell (Admin) session after creating a new hypver-v external switch with the name below:
minikube.exe start --vm-driver hyperv --hyperv-virtual-switch "ExternalSwitch"

# Need to fix VMQ, shutdown and disable VMQ and IPSec offloading

# Testing
kubectl.exe run hello-minikube --image=k8s.gcr.io/echoserver:1.10 --port=8080
kubectl.exe expose deployment hello-minikube --type=NodePort
kubectl.exe get pod # Repeat until status is Running
curl $(minikube service hello-minikube --url)

# Cleanup
kubectl delete services hello-minikube
kubectl delete deployment hello-minikube

```

### Notes

- Setup has only been tested on my laptop. Windows 10, using WSL for a linux distribution.
- I rely on Docker on Windows, which (according to some documentation I've found) would conflict with VirtualBox. Rather than invest time in getting this working I'm going to try mixing Windows PS commands with bash commands and denote where I do.
- I think I need to get kubectl and minikube setup to point to the windows installations.



