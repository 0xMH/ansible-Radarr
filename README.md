# Ansible-Radarr


An Ansible role the that deploys latest version of Radarr on most major linux Distributions. It's an **independent** fork from cmacrae.sonarr. 

## Requirements

* Ansible 2.0 or above

## Role Variables

Available variables are listed below, along with default values:

    Radarr_user_name: Radarr
    Radarr_group_name: Radarr
    Radarr_user_uid: 1006
    Radarr_group_gid: 1006
    Radarr_user_home: /opt/{{ Radarr_user_name }}
    Radarr_data_path: "{{ Radarr_user_home }}/data"
    Radarr_service_reload_command: systemctl daemon-reload
    Radarr_service_file:
      src: Radarr.service.j2
      dest: /etc/systemd/system/radarr.service
    Radarr_mono_gpg_key: http://keyserver.ubuntu.com/pks/lookup?op=get&search=0x3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
    Radarr_dependencies:
      - mono-devel
      
## Example Playbook

    - hosts: servers
      roles:
        - role: MoHD20.Radarr

## Usage
This section is for new comers, skip it if you like.

**Step1:**

Install [Ansible](http://docs.ansible.com/ansible/latest/intro_installation.html) in your system.

**step2:**

Install the role using:
 
    $sudo ansible-galaxy install MoHD20.Radarr
    
**step3:**

Make an `inventory` file the use this template:

    [servers]
    host1 ansible_ssh_host=someIP  ansible_ssh_user=someuser ansible_ssh_pass=somepassword ansible_sudo_pass=sudopassword

to add your server. you can add as many servers as you like. just change IP and passwords.

**step4:**

Make a `playbook` file let it be named `raddar.yaml`. Then copy-paste this play.

    - hosts: servers
      roles:
        - role: MoHD20.Radarr
        
**step5:**

Use this command:

    ansible-playbook raddar.yaml -i inventory

## License

MIT
