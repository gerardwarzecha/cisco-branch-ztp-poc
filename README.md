# Automate Network Configuration with AI 

## 1. Overview

This project demonstrates how AI assistants, such as ChatGPT, can be used to automate network device configuration in remote branch offices.
The solution uses Ansible and Jinja2 configuration templates.
All configuration data, such as hostnames, IP addresses and MPLS bandwidth values, is provided to the ChatGPT in the form of an Excel spreadsheet.

## 2. Business problem

Manual network device configuration is time-consuming and prone to human errors. Wherever possible network tasks should be automated. One example is remote branch offices, which often use a common configuration template and differ specific parameters like hostname, IP address, MPLS bandwidth. On the market we have a few solutions like: Cisco Catalyst Center, Cisco IQ, Juniper Mist AI, Meraki Dashboard. However, these solutions often have limited AI functionality or are still in early stages of AI implementation.

## 3. Solution Architecture
 
 ChatGPT using free license prepares two elements:
 
    3.1 Jinja2 configuration template ---> as a result, we get one configuration template for all branch routers.
    3.2 Hosts file for Ansible based on spreadsheet (excel) ---> as a result we get hosts file including all important parameters for every branch office like (IP address, hostname and MPLS bandwidth).
    
    Generally ChatGPT was used to:

- Generate Jinja2 templates
- Generate Ansible inventory
- Calculate QoS shaping values
- Transform spreadsheet data into structured automation data for Ansible

***

## Input Dataset

The input dataset contains 20 branch locations with:

- Branch name
- MPLS bandwidth
- Management IP address
- WAN IP address

Example:

| Branch | MPLS | MGMT IP | WAN IP |
|---------|---------|---------|---------|
| Gdańsk | 20 Mbps | 10.0.0.11 | 172.16.100.1/30 |
| Poznań | 25 Mbps | 10.0.0.27 | 172.16.100.5/30 |
| Łódź | 18 Mbps | 10.0.0.43 | 172.16.100.9/30 |


## 4. Network Topology

```text
                         MPLS / ISP Network Infrastructure
                                  |
    ----------------------------------------------------------------
    |              |              |               |               |
    |              |              |               |               |
router-gdansk  router-poznan  router-lodz   ...  router-plock
    |              |              |                       |
    |              |              |                       |
 VLAN10         VLAN10         VLAN10                  VLAN10
 VLAN11         VLAN11         VLAN11                  VLAN11
 VLAN12         VLAN12         VLAN12                  VLAN12
```


## 5. Workflow

Excel 
↓ 
ChatGPT 
↓ 
Jinja2 Templates 
↓ 
Ansible Inventory 
↓ 
Ansible Playbook 
↓ 
Cisco Branch Routers

## 6. Results

```text
PLAY RECAP ***********************************************************************************************************************************************

router-gdansk-01          : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-poznan-01          : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-lodz-01            : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-wroclaw-01         : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-szczecin-01        : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-lublin-01          : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-bialystok-01       : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-katowice-01        : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-rzeszow-01         : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-torun-01           : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-bydgoszcz-01       : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-opole-01           : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-kielce-01          : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-olsztyn-01         : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-zielona-gora-01    : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-radom-01           : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-gdynia-01          : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-zakopane-01        : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-tarnow-01          : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
router-plock-01           : ok=1    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```


## 7. Technologies

- Cisco IOS
- Ansible
- Jinja2
- Git
- GitHub
- ChatGPT

---
Gerard Warzecha

Network Automation
Infrastructure as Code
Cisco IOS
Ansible
AI - ChatGPT

