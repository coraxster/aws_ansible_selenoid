

## start instance
```
ansible-playbook playbook-start.yml --extra-vars "build_tag=build123 suite_tag=ignite2"
```

## stop instance
```
ansible-playbook playbook-stop.yml --extra-vars "build_tag=build123 suite_tag=ignite2"
```

## stop all suite instances
```
ansible-playbook playbook-stop-suite.yml --extra-vars "suite_tag=ignite2"
```

## stop ALL instances started by playbook-start.yml
```
ansible-playbook playbook-stop-all.yml
```