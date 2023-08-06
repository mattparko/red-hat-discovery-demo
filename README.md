## Set up a Red Hat Discovery demo / test lab

### Prereqs
1. Deploy an "AWS Blank Open Environment" in RHPDS (under Red Hat Open Environments)
2. Export the following environment variables (add your credentials and update region as needed)
    ```
    export AWS_ACCESS_KEY_ID=my_access_key_id
    export AWS_SECRET_ACCESS_KEY=my_secret_access_key
    export AWS_REGION=ap-southeast-2
    export REGISTRY_USER=my_registry_redhat_io_user
    export REGISTRY_PASS=my_registry_redhat_io_password
    export ADMIN_PASSWORDS=a_super_secret_password_for_RH_Discovery_services
    ```
3. Install Ansible dependencies on control node
   - ansible-core (tested on 2.14)
   - python3-boto
   - python3-boto3
   - python3-passlib
4. Install Ansible collections
   ```
   ansible-galaxy install -r requirements.yml
   ```
5. Ensure you have a public ssh key located at `~/.ssh/id_rsa.pub`

### Deploy and configure Red Hat Discovery
1. Execute `ansible-playbook site.yml`
2. Log in to Red Hat Discovery GUI
   1. Add credentials
   2. Add sources
   3. Execute a scan

### Destroy EC2 instances
1. Execute `ansible-playbook remove_ec2_instances.yml`

### Notes
1. These playbooks can be run multiple times
2. Be careful with your password management! The dsc-user password will enable remote and privileged password-based ssh to the EC2 instances
