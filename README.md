# Ansible NginX, Node.js playground

## General idea
I tried to figure it out how to setup production server and all it's dependecies to host nodejs
nodejs app(s). Idea for developer is just to setup config for nodejs app and state virtual hosts, and hit ansible...

which is going to setup NginX, Node.js, desired modules for Node and setup auto (beta|production)
deploy of the app.

After initial config and setup, developer should just work on it's app...

### Requiroments
* sshpass

### Hosts file
In the hosts file you shuld put your servers and vars.

**Example:**
```
[vagrant]
127.0.0.1

[vagrant:vars]
ansible_ssh_user=vagrant
ansible_ssh_pass={{ vagrant_ssh_pass }}
ansible_ssh_port=2222
ansible_python_interpreter=/usr/bin/python3
```

### Test config initially
```
ansible vagrant -m ping --extra-vars='vagrant_ssh_pass=::PLACE YOUR PASS HERE::'
```