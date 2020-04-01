# ios_upgrade
This Ansible playbook runs upgrade task for Cisco IOS/XE.

The playbook REBOOT the Router !!!!

> Contact information:\
> Email:    iarno.pagliani@gmail.com\
> Twitter:  @iarnopagliani

  * [IOS Image](#ios-image)
  * [Variables](#variables)
  * [Command](#command)
  * [Vault Password](#vault-password)
  * [Supported Platforms](#supported-platforms)
  * [Output Files](#output-files)
  * [Timeout](#timeout)

# IOS Image
IOS are not provided and they are stored outside git repository. Please download them from cisco.com
ios_path: `../images/gold/`

# Variables
- Debug switch used in the tasks; normaly False
    `debug: "False"`
- Used for skipping scp operations; normaly True
    `upload: "False"`

# Command
Use Command: `ansible-playbook upgrade_ios.yml`

Remenber to use verbose mode: `-v` or `-vv` or `-vvv` for ansible debug.

# Vault Password
Encrypt string commannd used:
`encrypt_string --vault-password-file ~/vault_pass_file.txt ansible`
where `ansible` is the password and `~/vault_pass_file.txt` is user defined

```
> cat ~/vault_pass_file.txt
secrect
```

# Supported Platforms
The playbook currently provides Ansible task files for Cisco IOS/IOS-XE ISR1101 and IR1101.
```
> ansible --version
ansible 2.9.6
```
# Timeout
A value of 1800 secs in task `ansible_command_timeout: 1800` has been configured for copy IOS file.

# Output Files
At the end of the playbook, the following filesystem components are created.
```
> tree
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
├── rtr_script.txt
├── templates
└── upgrade_ios.yml
```