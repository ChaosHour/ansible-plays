# ansible-plays



# Ansible version:
ansible --version

ansible [core 2.14.0]
  config file = None
  configured module search path = ['/Users/klarsen/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /Users/klarsen/.pyenv/versions/3.11.0/lib/python3.11/site-packages/ansible
  ansible collection location = /Users/klarsen/.ansible/collections:/usr/share/ansible/collections
  executable location = /Users/klarsen/.pyenv/versions/3.11.0/bin/ansible
  python version = 3.11.0 (main, Nov 21 2022, 19:57:48) [Clang 14.0.0 (clang-1400.0.29.202)] (/Users/klarsen/.pyenv/versions/3.11.0/bin/python3.11)
  jinja version = 3.1.2
  libyaml = True


# Accessing a list of dictionaries in Ansible 

```bash
(ansible-plays) ansible-playbook -c local -i 'localhost,' -e "v2=4.3.0" test.yml

PLAY [Test] ***************************************************************************************************************

TASK [Accessing list of dictionary] ***************************************************************************************
ok: [localhost] => (item={'version': '4.3.0', 'bundle': 'bundle-4.3.0.30967.tar.gz'}) => {
    "msg": " bundles version is 4.3.0 and bundle is bundle-4.3.0.30967.tar.gz"
}
skipping: [localhost] => (item={'version': '4.3.1', 'bundle': 'bundle-4.3.1.69410.tar.gz'})
skipping: [localhost] => (item={'version': '4.3.2', 'bundle': 'bundle-4.3.2.56823.tar.gz'})

TASK [Get extra vars from cmd-line] ****************************************************************************************
ok: [localhost] => {
    "msg": "4.3.0"
}

PLAY RECAP ******************************************************************************************************************
localhost                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
