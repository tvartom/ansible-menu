# ansible-role-menu
A menu to prompt the user for input as an Ansible-role.

# Reading resource: 
https://opencredo.com/blogs/reusing-ansible-roles-with-private-git-repos-and-dependencies/


Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }
    - name: "Menu"
        include_role:
          name: ansible-role-menu
          tasks_from: menu
        vars:
          menu:
           caption: "This is the caption of the menu!"
           question: "Choose alternative:"
           options:
             - name: "Alternative 1"  # Required
               value: 100             # Optional: Value to return in {{ menu_result }}, default value is {{ name }}
               option: "all"          # Optional: Option for user to choose
               default: true          # Optional: Is this alternative the default one?
             - name: "Alternative 2"
             - { name: "Alternative 3", value: 10 }

Return value is in the variable {{ menu_result }}

License
-------


Author Information
------------------


An optional section for the role authors to include contact information, or a website (HTML is not allowed).
