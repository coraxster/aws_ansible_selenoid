## Info
Ansible playbook.  
Starts new ec2 instance. Configure it as Selenium Selenoid Server. Saves instance address. And finaly terminate.  
Might be useful as ec2 Selenium Selenoid Servers provider for some sort of CI, testing platforms and so on.

### Require
Boto, Boto3, AWS-CLI, ec2 role with ability to manage ec2(via role asigned to instance or in ~/.aws/credential)... all things needed to start ec2 via aws-cli.

### Config
./group_vars/all.yml

## commands
build_tag - tag unique for 1 build/instance, using to start/stop particular instance  
suite_tag - tag unique for 1 build-suite, using to start/stop all instances of build-suite

#### start instance
```
ansible-playbook playbook-start.yml --extra-vars "build_tag=build123 suite_tag=ignite2"
```

#### stop instance
```
ansible-playbook playbook-stop.yml --extra-vars "build_tag=build123 suite_tag=ignite2"
```

#### stop all suite instances
```
ansible-playbook playbook-stop-suite.yml --extra-vars "suite_tag=ignite2"
```

#### stop ALL instances started by playbook-start.yml
```
ansible-playbook playbook-stop-all.yml
```