# ssh-hardening-fallback (Ansible role)

(Still in alpha stage. Not ready for production!)

## Description

Idempotent wrapper to dev-sec.ssh-hardening with automatic fallback to default port 22.

## Requirements

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

## Role Variables

No specific variables. But it does use inventory variable `ansible_port`. Also, being a wrapper to `dev-sec.ssh-hardening`, all variables relevant to that role will be applied. Please refer to its [documentation](https://github.com/dev-sec/ansible-ssh-hardening) for more details.

## Dependencies

It calls role `dev-sec.ssh-hardening`. When using this role, variable `ssh_server_ports` is not available since it will always be overwritten with the inventory variable `ansible_port`.

## Example Playbook

    - hosts: servers
      roles:
         - { role: nununo.ssh-hardening-fallback }

## License

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

## Author Information

* Author: Nuno Godinho
* Based on [this post](https://dmsimard.com/2016/03/15/changing-the-ssh-port-with-ansible/) by: David Moreau Simard
