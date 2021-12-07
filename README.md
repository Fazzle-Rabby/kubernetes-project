# DevOps Project with kubernetes-project

Developer > Git-Hub > Jenkins > Ansible > Kubernetes

# Send files or execute command over ssh

rsync -avh /var/lib/jenkins/workspace/kubernetes-project/*  root@172.31.4.131:/opt

# Send files or execute command over ssh

cd /opt
docker image build -t $JOB_NAME:v1.$BUILD_ID .
docker image tag $JOB_NAME:v1.$BUILD_ID fazzlerabby/$JOB_NAME:v1.$BUILD_ID
docker image tag $JOB_NAME:v1.$BUILD_ID fazzlerabby/$JOB_NAME:latest
docker image push fazzlerabby/$JOB_NAME:v1.$BUILD_ID
docker image push fazzlerabby/$JOB_NAME:latest
docker image rmi  $JOB_NAME:v1.$BUILD_ID  fazzlerabby/$JOB_NAME:v1.$BUILD_ID  fazzlerabby/$JOB_NAME:latest

# Send build artifacts over ssh

ansible-playbook /opt/ansible.yml
