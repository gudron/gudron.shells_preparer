gudron.shells_preparer
=========

Role for preprare user shell environment

Role Variables
--------------

### General variables
  * `to_prepare: list`
    List of shell's where the environment will be prepared.
    
    * `name: string` 
      The name of the user to configure the shell environment.

    * `shell: string` 
      The name of the shell for the environment will be prepared. 
      
      Currently supported `zsh`.
    
    * `shell_params: dict` 
      Dict with shell environment variables.

    * `plugins: list` 
      List of shell plugins will be installed.

    Full example: [defaults/main.yml](defaults/main.yml).

Example Playbook
----------------

    - hosts: example_project:&example_project_stage
      any_errors_fatal: "{{ any_errors_fatal | default(true) }}"
      gather_facts: True

      roles:
        - name: gudron.shells_preparer
          vars: 
            to_prepare:
              - name: exmaple_user
                shell: /bin/zsh
                shell_params:
                  ZSH_THEME: agnoster
                plugins:
                  - git
                  - docker-compose

License
-------

Apache
