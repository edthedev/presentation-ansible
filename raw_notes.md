
??? 
## Raw ideas

Example: Take inventory - versions, hosts in groups, hosts with certain software installed
Example: Apply updates on Ubuntu
Example: Apply updates on Windows

Idea: Add yes/no Puppet can do this, for most examples (or just highlight the bits that Puppet does not do.)
    Not to rag on Puppet, but to help people understand how Ansible is a more extensive product.

# The Developer and the Admin
## Can be Friends

???


# The Developer and The Admin can be Friends

## Admin Flaws
Worry too much.
Don't like having fun.

## Developer Flaws
Never write anything down.
Nothing they build works.

## Developer Lens
People need this to work, right now!
Deployment is boring, I don't want to think about it.

## Admin Lens
People need this to work tomorrow and every day after.
Deployment *should* be boring, we probably *should* think about it.

## Shared Lenses
I can't reliably do my job unless I know that what we tried to deploy got fully deployed, where it needs to go.

Ansible is a DevOps tool.
Other DevOps tools: PowerShell, MSI, RPM, Git, KShell
DevOps philosophy is that Development and Operations are a team.
    - Both should write Ansible Playbooks
    - Both should be able to run Playbooks
    - Both should be able to maintain playbooks

---

# Ansible Philosophy

---

# Example Playbook
.small[
```YAML
---
- hosts: webservers
  vars:
    http_port: 80
    max_clients: 200
  remote_user: root
  tasks:
  - name: ensure apache is at the latest version
    yum: name=httpd state=latest
  - name: write the apache config file
    template: src=/srv/httpd.j2 dest=/etc/httpd.conf
    notify:
    - restart apache
  - name: ensure apache is running (and enable it at boot)
    service: name=httpd state=started enabled=yes
  handlers:
    - name: restart apache
      service: name=httpd state=restarted
```
]

---

# Example Commands

Run a playbook:
```BASH
ansible-playbook playbook.yml
```

---

# Ansible Verbosity

```BASH
-VVVV
```

???

Also controls SSH verbosity.

---

# Bonus Slide: Make a Makefile

```Make
deploy:
    ansible-playbook playbook.yml

```

???

Not exactly what Make is for.
But pretty much what Make is for.
Even non-Make users can read your exact commands and even and paste them.

