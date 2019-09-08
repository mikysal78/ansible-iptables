Role Ansible-Iptables
=========

[![N|Solid](http://basilicata.ninux.org/images/Logo_Ninux_Basilicata_600-192.png)](http://basilicata.ninux.org)


Un semplice ruolo che apre le porte per SSH, OpenVPN, OLSRd2 e Bind Server. La modifica è molto semplice.


Role Variables
--------------

Puoi modificare le porta SSH di default nel file defaults/main.yml o impostarla nel playbook come nell'esempio. Le regole sono definite in task/main.yml ed è semplicissimo inserne nuove o modificare quelle esistenti.


Example Playbook
----------------

```
---
- hosts: All
  become: "{{ sudo | default('yes') }}"
  roles:
    - ansible-iptables
  vars:
    ssh_port: 2400
```

creare un file inventory dal nome hosts tipo questo esempio:
```
[firewall]
tux.basilicata.nnxx ansible_user=root ansible_port=2400 ansible_host=10.27.22.5
```
Lancia il playbook come ad esempio:
```
ansible-playbook -i hosts server.yml
```

License
-------

BSD

Author Information
------------------

[MikySal78](https://github.com/mikysal78)
