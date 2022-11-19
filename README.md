# Ansible KVMs

Is the experimental Ansible playbook to bootstrap cluster of Virtual Machines on the Linux Desktop or Server. The idea is to bootstrap Virtual Machines from JSON-file and it is designed use with the Kubespray. 

- https://kubernetes.io/docs/setup/production-environment/tools/kubespray/

roles/create_kvms/vars/kvms.json

        {
          "masters": [
            {
              "name": "node1",
              "ram_mb": 2048,
              "vcpus": "2",
              "disk_size": "20G",
              "pool_home": "/var/lib/libvirt/filesystems/",
              "ipv4": "192.168.152.11/24"
            }
          ],
          "workers": [
            {
              "name": "node2",
              "ram_mb": 2048,
              "vcpus": "2",
              "disk_size": "60G",
              "pool_home": "/var/lib/libvirt/filesystems/",
              "ipv4": "192.168.152.12/24"
            },
            {
              "name": "node3",
              "ram_mb": 2048,
              "vcpus": "2",
              "disk_size": "60G",
              "pool_home": "/var/lib/libvirt/filesystems/",
              "ipv4": "192.168.152.13/24"
            },
            {
              "name": "node4",
              "ram_mb": 2048,
              "vcpus": "2",
              "disk_size": "60G",
              "pool_home": "/var/lib/libvirt/filesystems/",
              "ipv4": "192.168.152.14/24"
            }
          ],
          "base_image_url": "https://cloud.debian.org/images/cloud/bullseye/latest/debian-11-genericcloud-amd64.qcow2",
          "base_image_name": "debian-11-genericcloud-amd64.qcow2",
          "base_image_checksum": "sha512:71f1c376e585a87299f751e076689d7ebe2a897649b65071878eb5694be76b771f37c21d7a88630214f4650dec5307e9f73d597ec326f99bd3451e23f607e5b8",
          "image_pool_dir": "/var/lib/libvirt/images",
          "clusterName": "k8sDev",
          "network": {
            "ipv4Address": "192.168.152.0",
            "ipv4_gateway": "192.168.152.1",
            "ipv4_mask": "255.255.255.0",
            "domainName": "k8s-dev.local"
          }
        }
## Roadmap


