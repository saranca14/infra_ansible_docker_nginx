# infra_ansible_docker_nginx
Setting up a Nginx docker container on remote server with Ansible

```
root@ip-10-0-1-142:/project/infra_ansible_docker_nginx# ansible-playbook ansible/site.yml -i ansible/hosts.yml

PLAY [Configurations to "remote" host] **********************************************************************************************************************

TASK [Gathering Facts] **************************************************************************************************************************************
ok: [remote]

TASK [setup : Update apt packages] **************************************************************************************************************************
changed: [remote]

TASK [setup : Import docker tasks] **************************************************************************************************************************
included: /project/infra_ansible_docker_nginx/ansible/roles/setup/tasks/docker.yml for remote

TASK [setup : Install docker packages] **********************************************************************************************************************
ok: [remote] => (item=[u'apt-transport-https', u'ca-certificates', u'curl', u'software-properties-common'])

TASK [setup : Add Dockers official GPG key] *****************************************************************************************************************
ok: [remote]

TASK [setup : Verify that we have the key with the fingerprint] *********************************************************************************************
ok: [remote]

TASK [setup : Set up the stable repository] *****************************************************************************************************************
ok: [remote]

TASK [setup : Update apt packages] **************************************************************************************************************************
changed: [remote]

TASK [setup : Install docker] *******************************************************************************************************************************
ok: [remote]

TASK [setup : Create "docker" group] ************************************************************************************************************************
ok: [remote]

TASK [setup : Add remote "ubuntu" user to "docker" group] ***************************************************************************************************
ok: [remote]

TASK [setup : Install docker-compose] ***********************************************************************************************************************
ok: [remote]

TASK [setup : Remove useless apt packages from the cache] ***************************************************************************************************
ok: [remote]

TASK [setup : Remove dependencies that are no longer required] **********************************************************************************************
ok: [remote]

PLAY [Copying "docker" application folder on remote server] *************************************************************************************************

TASK [Gathering Facts] **************************************************************************************************************************************
ok: [remote]

TASK [Copy "docker" application folder across] **************************************************************************************************************
ok: [remote]

TASK [app : Rebuild images defined in compose file and restart containers whose images have changed] ********************************************************
changed: [remote]

PLAY [Setting up logrotate for Nginx container] *************************************************************************************************************

TASK [Gathering Facts] **************************************************************************************************************************************
ok: [remote]

TASK [Create logrotate for container] ***********************************************************************************************************************
changed: [remote]

PLAY RECAP **************************************************************************************************************************************************
remote                     : ok=19   changed=4    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```
