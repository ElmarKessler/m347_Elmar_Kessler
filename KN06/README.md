## A
### Master
![](Master.PNG "")
### Node 1
![](Node1.PNG "")
### Node 2
![](Node2.PNG "")
## B
### Status
![](Status.PNG "")
### Node entfernen
Ich entferne den Node mit microk8s leave
![](Leave.PNG "")
### Node 1 als Worker 
Hier erstelle mache ich einen Node als Worker (--worker)
![](NodeAlsWorker.PNG "")
### Node hinzufügen als Worker und microk8s status
![](WorkerNodeNot.PNG "")
### Befehl microk8s status (vor addons)
![](ZweiterStatus.PNG "")
### Erkenntinis
```
Der wesentliche Unterschied besteht darin, dass ein High-Availability Cluster mehrere Nodes umfasst, die redundant sind, sodass im Falle eines Ausfalls eine andere Node die Arbeit übernehmen kann. Die IP-Adressen der verbundenen Nodes werden angezeigt, um den Status von Kubernetes zu beschreiben und zu zeigen, welche Nodes verbunden sind und welche Rolle sie einnehmen. Zusätzlich werden die hinzugefügten Add-ons angezeigt.

Mit MicroK8s kann man einzelne Nodes in einem Cluster verwalten, während man mit kubectl das gesamte Cluster bearbeitet, das aus mehreren Nodes besteht. Um das Cluster zu bearbeiten, muss man spezifisch "microk8s kubectl" verwenden.
```
### Cloud-init.yaml
#cloud-config
# source: https://thenewstack.io/deploy-a-kubernetes-cluster-on-ubuntu-server-with-microk8s/
users:
  - name: ubuntu
    sudo: ALL=(ALL) NOPASSWD:ALL
    groups: users, admin, microk8s
    home: /home/ubuntu
    shell: /bin/bash
    ssh_authorized_keys:
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCUBo+qnNu5xxM9vfz4C04M36FHxHNrEMdm5TkFj1/SfVtqunlUOeMpu7nFCZZKnX8HYwf/MkjcBiTYAgncxku8grwl6XuW/pcvmb6/ghSIaw4xtRRSzit7omqJ5d8kXB3+Nd1aaMHsjfly4nkaqswhySVXQqr8Hw6DbWVw8jLLVKEE+5NZHY33hJkhJwK4blCllsGpmQaKi1qxjsN0hZOWNK01iJAydwD8t2xJ0NOYbq8Qas5IyPnRN7SPxvEhIP6WLQ6Ym6Dmf8FwNW1cHLTKabgjzt5f/HKUkKS89dPd3fn4nnFli1BOMECGUIvVlOw2pQNri7+04OOfn2FGlqr5 teacher
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDC189VB6syefxTIoxUOEQGLP2PE9g5YjwPtGWtVsWMgXzrhID/2JqcX9RpCdctOiVOo4JjmtwbZ1gChQ/n/eH5Rvaq1GmqDlNFIPJrzDIFvjiA9fVvL0W8nxF0N4AVjpIX+1RFRUQWUxuTHDG9nkF8dPIslbwfBsRMJZwBiRBsrLoyEvCRE8A9DQ21fQjRTXkRwuZdE7cG6rJKrptBO9MqFK9jdj3hW0E1KIdm2n175Bl7aY5NgWc5K0I/lHeV3649qXVFYKnw+y7Qo1oqxmhO3qNxKoL/jue9uA+Kq12LNcEbuRqPdjE0cBS2sSTBiK8ID77uaONDQsuE0ZaTu6Nr aws
groups:
  - microk8s
system_info:
  default_user:
    groups: [microk8s]
ssh_pwauth: false
disable_root: false
package_update: true
package_upgrade: true
packages:
  - curl
runcmd:
  - sudo snap install microk8s --classic
  - mkdir /home/ubuntu/.kube
  
  
