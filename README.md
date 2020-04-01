# ios_upgrade
This Ansible playbook runs upgrade task for Cisco IOS/XE

> Contact information:\
> Email:    iarno.pagliani@gmail.com\
> Twitter:  @iarnopagliani

  * [IOS_image](#IOS_Image)
  * [Variables](#Variables)
  * [Command](#Command)
  * [Supported platforms](#supported-platforms)
  * [Output files](#output-files)
  * [Timeout](#Timeout)

# IOS_Image
IOS are not provided and they are stored outside git repository. Please download them from cisco.com
ios_path: "../images/gold/"

# Variables
- Debug switch used in the tasks; normaly False
    `debug: "False"`
- Used for skipping scp ioperations; normaly True
    `upload: "False"`

# Command
Use Command: ansible-playbook update_ios.yml 
Remenber to use verbose mode: -v or -vv or -vvv for ansible debug

# Supported platforms
The playbook currently provides Ansible task files for Cisco IOS/IOS-XE ISR1101 and IR1101.
```
> ansible --version
ansible 2.9.6
```
# Timeout
A value of 1800 secs in task `ansible_command_timeout: 1800` has been configured for copy IOS file
# Output files
At the end of the playbook, the following filesystem components are created.
```
tree
.
├── README.md
├── RN
│   └── IR1101-release-notes-16-12-3.pdf
├── ansible.cfg
├── config
│   └── 2020-04-01_R1_facts.cfg
├── group_vars
│   ├── all.yml
│   ├── ir1101.yml
│   └── isr1101.yml
├── host_vars
├── hosts.yml
├── reload_ios.yml
├── rtr_script.txt
├── templates
└── update_ios.yml
```