# Package Management.
* go mod init project_name [Initializes project.]
* go get package_name
* go list -m all [List all the dependencies .]
* go list -m version dependency_name [Will list the dependency version being used.]
* go mod tidy [Remove unsed dependencies]
* GO111MODULE=on/off/auto [To turn off/on/auto GOMOD. In auto mode similary to GO111MODULE=on when you're outside of GOPATH, similarly to GO111MODI ] 

# MongoDB.
* Checkout this solution but first try below command: https://askubuntu.com/questions/856073/mongod-unrecognized-service-mongod-service-is-present-already
* Start mongodb : sudo mongod --fork --logpath /var/log/mongodb.log

# Git Commands.
* git branch -v
* git checkout -b new_branch_name  
* git checkout branch_to_switch
* git status
* git log
* git add .
* git commit -m "your_message"
* git push origin branch_name
* git diff
* git remote add origin https://github.com/vibhordubey333/GITCheatSheet.git
* git remote set-url origin https://github.com/vibhordubey333/GITCheatSheet.git
* git branch -d localBranchName  // delete branch locally 
* git push origin --delete remoteBranchName // delete branch remotely
* To sync changes with master branch or other branch -> git pull origin branch_name

## Rebase [To sync the changes with other branch.]
* git checkout feature/movies_comment
* git rebase master

# Linux
* Killing process by providing process ID: kill 1293
* Killing process by providing process name : pkill firefox
* Running process in background : firefox&
* Find if port is in use : netstat -apn | grep 7777
* scp file_name root@172.90.91.120:/tmp

## Session in Linux
* Check session : who 
* Detailed information : w
* If multiple users are using like liteide then : pkill liteide
* To crash other people session identify shell they are using then: pkill bash

## Removing and Installing packages in Linux.
* sudo apt-get remove golang-1.6-src
* dpkg --list | grep golang-1.6-src
* dpkg -i package_to_install

## Grep and Find
* grep -inr "search_tring"
* grep -inrw "search_string"
* find / -name "file_name_to_search"

## Dpkg fix.
* sudo dpkg --configure -a   [Instruct dpkg to fix iteself.]
  - sudo apt-get -f install  [Correct dependecies problem.]
  - sudo apt install libavahi-glib1 --reinstall [Reinstall the problamatic package.]

## Installing minikube on VirtualMachine(Os: Antix) , Host : windows 7

* Disable virtualization(VT-X/AMD-v) and PA-NX in virtual machine . As windows 7 doesn't have VT-X flag if it has in your case disable it.
* sudo apt install conntrack
* sudo minikube start --driver=none

## K8s commands.

* kubectl exec -tin test mongoPodName -- mongo
* kubectl port-forward -n test service/sfc-service 10128:10128 --address=0.0.0.0
* kubectl get po --all-namespaces |  grep auth
* kubectl get pods --namespace namespace_name  [To search in a particular namespace]
* kubectl describe pods --namespace namespace_name [To describe all pods from a namespace]
* kubectl describe pods pod-name --namespace namespace-name [To describe a specific pod.] 
* kubectl get pods --namespace namespace_name --watch  [To search in a particular namespace and watch them as there status change]
* kubectl delete pv -n imec-test [Deleting persistant volume.]
* kubectl delete pod pod-name --namespace namespace_name
* kubectl delete pod pod_name
* Kubernetes error "The connection to the server <host>:6643 was refused:"
  - sudo -i && swapoff -a && exit
  - strace -eopenat kubectl version
* kubectl logs pod_name -n namespace_name > log.txt

# HelmChart
* helm uninstall test -n test && helm uninstall test -n imec-test

# Docker.
* To save an Image locally as tar : docker save hello-world > hello-world.tar 
* To extract above tar : tar -xfv hello-world.tar'

# Swagger.
* ./swagger_windows_amd64 generate server -f ./api/sfc_swagger.yml -A sfc



