# SSHkey-to-AWSregions
[![Builds](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

----
## Description
This is a localhost ansible playbook to create and import SSH key pair to multiple AWS regions so that we could use the same set of key pair for instances provisioning in multiple regions. This would require either AWS console root account ACCESS/Secret key or you could create an AWS programmatic IAM user with limited privilege and use its ACCESS/Secret key to communicate.

**Note:**  *This is currently only works within RPM based Linux Operating Systems [For eg: CentOS, AmazonLinux2, AlmaLinux, RHEL, RockyLinux]. I'll add the rest very soon.*

----
## Steps to Use
- Install **[Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html "Ansible")** on your device

- Create a [**programmatic IAM user**](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html#id_users_create_console "programmatic IAM user") in AWS console 

- Run the following commands to install required Ansible collections (Official)
```bash
ansible-galaxy collection install community.crypto
ansible-galaxy collection install amazon.aws
```

- Install **[Git](https://github.com/git-guides/install-git "Git")** package in your device

- Run the following commands:

```bash
git clone https://github.com/fasalsh/SSHkey-to-AWSregions.git
cd SSHkey-to-AWSregions

# Enter the ACCESS/Secret  key, Key pair name, regions in credentials file
# access_key: "AWS Console access key here"
# secret_key: "AWS Console secret key here"
vim credentials.vars

# To create and import SSH key pair, run this:
ansible-playbook create_import_key.yml

# To remove the key pair from multiple regions, run this:
ansible-playbook remove_key.yml
```
----
## Features:

- Very easy to create and deploy SSH key pairs to multiple AWS regions
- Easy to remove specific SSH key pair from multiple AWS regions
- Supported in all RPM based Distros (will add rest)
- Easy to handle regions and SSH key pair name 

----

## Reference:
- AWS Region List: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RegionsAndAvailabilityZones.html

## Issues/Requests:
- If you encounter any issues with this, open an issue in Github
- If you wish to work on it further, feel free to fork and make it better or add a pull request once added new features.

Thanks
*Fasal Muhammed*
