# Minikube

## Installation

### Installation Process

```bash
# Install Kubectl on PS:
choco install kubernetes-cli

# Installing v 0.28.0 for Windows x64 and dropping the exe in a folder on both my Windows and WSL installations' path variables.
curl https://github.com/kubernetes/minikube/releases/download/v0.28.0/minikube-windows-amd64 > ~/bin/minikube.exe && chmod +x ~/bin/minikube.exe

# Because of my setup, the following was run in a powershell (Admin) session after creating a new hypver-v external switch with the name below:
.\bin\minikube start --vm-driver hyperv --hyperv-virtual-switch "Primary Virtual Switch"

# Testing
kubectl run hello-minikube --image=k8s.gcr.io/echoserver:1.10 --port=8080

```

### Notes

- Setup has only been tested on my laptop. Windows 10, using WSL for a linux distribution.
- I rely on Docker on Windows, which (according to some documentation I've found) would conflict with VirtualBox. Rather than invest time in getting this working I'm going to try mixing Windows PS commands with bash commands and denote where I do.
- I think I need to get kubectl and minikube setup to point to the windows installations.



