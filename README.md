## Set up a Red Hat Discovery demo / test lab

### Prereqs
1. Deploy an "AWS Blank Open Environment" in RHPDS (under Red Hat Open Environments)
2. Export the following environment variables (add your credentials and update region as needed)
    ```
    export AWS_ACCESS_KEY_ID=myaccesskeyid
    export AWS_SECRET_ACCESS_KEY=mysecretaccesskey
    export AWS_REGION=ap-southeast-1
    ```
3. Install Ansible dependencies on control node
   - ansible-core 2.14
   - python3-boto
   - python3-boto3
4. Install Ansible collections
   ```
   ansible-galaxy install -r requirements.yml
   ```
5. Ensure you have a public ssh key located at `~/.ssh/id_rsa.pub`

### Deploy
1. Execute `ansible-playbook site.yml`

### Notes
1. This playbook can be run multiple times
2. You can start/stop your EC2 instances with the provided playbooks
