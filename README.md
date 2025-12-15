# Nextcloud Private Cloud using K3s and GlusterFS

This repository contains the complete configuration and deployment files for setting up a **private cloud storage system** using **Nextcloud**, **Kubernetes (K3s)**, and **GlusterFS**. The project demonstrates how cloud-like services can be built using open-source tools on commodity hardware while maintaining full data ownership and privacy.

Project Overview

The objective of this project is to design and deploy an **private cloud** that provides secure file storage, synchronization, and collaboration services. The system is built entirely using open-source technologies and is suitable small-scale organizational deployments.


Architecture Summary

 **Cloud Type:** On-Premises Private Cloud  
 **Orchestration:** Kubernetes (K3s)  
 **Storage:** GlusterFS (Distributed File System)  
 **Application:** Nextcloud  
 **Database:** MariaDB  

Cluster Configuration
 **Master Node IP:** 192.168.29.238  
 **Worker Node IP:** 192.168.29.118  

 Note: The architecture supports high availability conceptually. However, due to hardware constraints, the actual deployment uses one master and one worker node.



File Description

 File Name                         Description 
 
 `K3s_installation.yaml`           Installation and configuration steps for K3s master and worker nodes |
 `nextcloud_k3s_glusterfs.yaml`    Main deployment file for Nextcloud and MariaDB using GlusterFS
 `nextcloud_glusterfs_ha.yaml`     High Availability design with replica-based deployment 
 `nextcloud-rwo.yaml`              Alternative deployment using ReadWriteOnce volumes 
 `README.md`                       Project documentation 



 Prerequisites

Ensure the following requirements are met before deployment:

- Ubuntu Linux installed on all nodes
- K3s installed and running on master and worker nodes
- `kubectl` configured on the master node
- Static IP addresses assigned to all nodes
- GlusterFS volume created and mounted on **all nodes** at:
  - `/mnt/gv0/data/mariadb`
  - `/mnt/gv0/data/nextcloud`



