# akraino-ansible
===

Ansible playbooks and roles for deployment Akraino Regional Controller and treasuremap with Tungstenfabric on AWS cloud

Install awscli and boto


put this in your ~/.boto files
~~~
[Boto]
use_endpoint_heuristics = True
~~~

setup AWS credentials 

---

Deployment stages

Creating 2 AWS instances and updating inventory and group_vars.
private key aws-private.pem appears in this directory

~~~
   ansible-playbook deploy_ec2_hosts.yaml 
~~~

Deployment Akraino RC and creating DAG for treasuremap deployment
~~~
   ansible-playbook -i hosts deploy_akraino_rc.yaml 
~~~


Terminating AWS instances and cleanup inventory and group_vars
~~~
   ansible-playbook -i hosts terminate_ec2_instances.yaml
~~~
