# ansible-cd

## CD pipeline using Ansible and Docker

#### ansiblecdbuild.yml
The playbook 'ansiblecdbuild.yml' will clone the git repository. (https://github.com/jobygit/ansible-cd-content) to the localhost and will create docker image.This docker image will be pushed to the docker repository\
Tags given in the github commit will be fetched and docker images created will get these tags.The ansiblecdbuild.yml will build new docker image only if any new changes have been committed in the github repo.\
If a new change is commited with tagname 'V2' in the github, the playbook will create docker image jobyzac/ansiblecd:V2 and jobyzac/ansiblecd:latest

#### deploy.yml
This playbook will download the latest docker image and run a docker container on the custom host server, can be production servers.
