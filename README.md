# Ansible-Radarr


An Ansible role the that deploys latest version of Radarr on most major linux Distributions.

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
        - role: MoHD20.radarr



## License

MIT