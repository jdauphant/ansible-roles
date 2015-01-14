ansible-roles
=============

Regroupment of all my Ansible roles with git submodule + Informations

Add this variables to you ansible.cfg 
    roles_path= /path/to/ansible-roles

# Role conventions
- Git repository name are : ansible-role-rolename
- task name
   - all task should have a name description
   - all task name should tourn in form of ensure the state is ok and not made the action
   - the task name don't have to include the role name
   - Examples :
      - Good task name: Ensure python and python-api are installed
      - Bad task name: python | installation of python
- tags
   - all tasks should be tag by the role name
   - other standart tags are : deploy,compilation,packages,configuration,service
   - tags sould set at the end of the task with this yaml form : tags: ["rolename","configuration"]
- OS
   - all tasks with OS or family OS dependency should have a when condition on ansible_os_family or ansible_distribution
      - especially for packages manager task
   - you don't have to support all OS if you can't test it
   - place OS specific task in different file if it's more than 1 task
- sudo
   - use sudo only when it's not for root user
 
