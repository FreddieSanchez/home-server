The following should be configured before beginnning. 

* Public SSH key on your server:
```
  ssh-keygen -t rsa
  ssh <server> 'mkdir -p .ssh'
  cat id.pub >> | ssh <server> 'cat >> .ssh/authorized_keys'
```


* Run each playbook: 
```
   # sets up the network
   ansible-playbook -i inventory network/main.yml
   # sets up the environment
   ansible-playbook -i inventory common/common.yml
   # sets up server level configuration
   ansible-playbook -i inventory node/ps1/playbook.yml
```

