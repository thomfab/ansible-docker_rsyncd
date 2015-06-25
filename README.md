Rsync deamon running in docker
==============================

This role creates a docker container running the rsync deamon (rsyncd)
The docker container used is : thomfab/docker-rsyncd (https://registry.hub.docker.com/u/thomfab/docker-rsyncd/)

Role Variables
--------------

Several variables can be set up.

The name used for the docker container :
  docker_rsyncd_dockername: "rsyncd"

The user and group used as the owner of the rsync folder
  docker_rsyncd_user: "myuser"
  docker_rsyncd_userid: 1001
  docker_rsyncd_group: "users"
  docker_rsyncd_groupid: 100

Configuration information for the rsync deamon :
Name of the rsync deamon :
  docker_rsyncd_deamonname: "rsync"

Port used for the rsync deamon :
  docker_rsyncd_port: 873

Folder where files sync :
  docker_rsyncd_dir: "/mnt/rsync"

Example Playbook
----------------

Example :

    ---
    - hosts: servers
      roles:
        - role: thomfab.ansible-docker_rsyncd
          docker_rsyncd_dockername: "rsyncd"
          docker_rsyncd_user: "myuser"
          docker_rsyncd_userid: 1001
          docker_rsyncd_group: "users"
          docker_rsyncd_groupid: 100
          docker_rsyncd_deamonname: "rsync"
          docker_rsyncd_port: 873
          docker_rsyncd_dir: "/mnt/rsync"


License
-------

BSD
