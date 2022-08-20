# Ansible Role: OCP HAProxy

Installs HAProxy and configures an API and ingress load balancer for OpenShift Container Platform.

## Requirements

None.

## Role Variables

Available variables are listed below (see `defaults/main.yml`):

    haproxy_ports: []

    haproxy_domain_name: ""

    haproxy_api_server_nodes: []

    haproxy_ingress_nodes: []


## Dependencies

None.

## Example Playbook

      hosts: loadlbalancer
      vars:
        haproxy_ports:
          - 80
          - 443
          - 6443
          - 22623
        haproxy_domain_name: example.com
        haproxy_api_server_nodes:
          - name: bootstrap
          - name: control-1
          - name: control-2
          - name: control-3
        haproxy_ingress_nodes:
          - name: compute-1
          - name: compute-2
          - name: compute-3
      roles:
        - { role: haproxy }