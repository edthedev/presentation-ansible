## Intro
What is Ansible
    Introduce/ explain the name Ansible
Our Experience with Ansible

## Why Bother With Ansible?
As a developer, I need to know that my problem was not the deployment.
I need boring push-ups.
        Ansible is reliable and repeatable. 
        File copy is reliable and repeatable, but deployment is a lot more than file copy.
        Deployment is: file copy, permissions, web config, app config, host dependencies, host config

As an administrator...?


## Things Ansible Does (With Examples)
Update a custom web app
Harden security settings
Install EPEL
Setup networking
Provision a new AWS host!
Create user accounts
Update Windows (New)

## Get Started with Ansible
Show a Hosts file.

Show Ansible Galaxy
    Mention and link to Jeff Gearling and Burt VV - creators of great Ansible roles

Give example commands to check out a playbook from Ansible galaxy.

Show the -VVVV flag. (Debug your playbooks)
Link a Guide to SSH. (Use it to do anything Ansible cannot yet do)

Give example commands to contribute to an Ansible Galaxy playbook.
    Or Link to a Guide to Git? (Use it to track / share your own work.)

## Raw ideas

Example: Take inventory - versions, hosts in groups, hosts with certain software installed
Example: Apply updates on Ubuntu
Example: Apply updates on Windows

Idea: Add yes/no Puppet can do this, for most examples (or just highlight the bits that Puppet does not do.)
    Not to rag on Puppet, but to help people understand how Ansible is a more extensive product.