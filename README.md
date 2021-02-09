## Three tier application

This set of Ansible playbooks fully install and configure Ansible Tower and also create required resourcess in Ansible Tower to automatically deploy three-tier application in QA and Prod environment.


| Files or dir | Purpose|
-----------|-------------|
| app-tier | Install application server role|
| db-tier  | Install postgressql server for database role|
| lb-tier  | Install HA proxy role|
| base-config | Setup yum repo and base packages role|
| setup-workstation | Setup workstation, create network, ssh keypair, security group etc. role |
| osp-servers | Provision OSP Instances role|
| osp-instance-delete | Delete OSP Instances role|
| osp-facts | Genrate in-memory inventory for OSP instances role|
| roles/config-tower/vars/main.yml | Very important file to review. All the variable values are set there. Please do not make any changes in the file||
| config-tower | Role to configure ansible tower job templates and workflow|
| aws_creds.yml | Fetch GUIDkey.pem from bastion of Three tier application env and create machine credential to connect to AWS instances|
| aws_provision.yml | Use `order_svc.sh` script to provision env|
| aws_status_check.yml | Check aws instances are up or not|
| site-3tier-app.yml | Playbook to deploy three tier app|
| site-install-isolated-node.yml | Playbook to install isolated node|
| site-config-tower.yml | Playbook to call role `config-tower`|
| site-osp-delete.yml | Playbook to call role|
| site-osp-instances.yml | Playbook to call role|
| site-setup-prereqs.yml | Playbook to call role|
| site-smoke-osp.yml | Playbook to test three tier app on OSP|
| site-smoketest-aws.yml | Playbook to test three tier app on AWS|
| grading-script.yml | Self grading script|
| roles/config-tower/tasks/ec2_dynamic.yml | For creating Dynamic inventory in Ansible tower. Use `AWS Access Key` for credential|
| roles/config-tower/tasks/job_template.yml | For creating job templates|
| roles/config-tower/tasks/pre-config-tower.yml | Any pre config tasks needed|
| roles/config-tower/tasks/workflow_template.yml | genrate workflow from `workflow.yml` file|
| roles/config-tower/tasks/post-config-tower.yml | any post config jobs

