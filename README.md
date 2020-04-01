# ios_upgrade
Use Ansible playbook for upgrade Cisco IOS
Ver 0.1
# IOS image
IOS are not provided and they are stored outside git repository. Please download them from cisco.com
variable referece on 
group_vars/all.yml
 ios_path: "../images/gold/"

Use Command: ansible-playbook update_ios.yml 
