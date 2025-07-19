<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Launch a Kubernetes Cluster

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-eks1)

**Author:** Melvin J Bonner  
**Email:** melvinj.bonner@gmail.com

---

## Launch a Kubernetes Cluster

![Image](http://learn.nextwork.org/zealous_maroon_serene_raspberry/uploads/aws-compute-eks1_e5f6g7h8)

---

## Introducing Today's Project!

In this project, I will deploy my first Kubernetes cluster because I want to learn what it does and why people love it.



### What is Amazon EKS?

Amazon EKS is a managed service that makes it easy to run Kubernetes on AWS without needing to maintain your own Kubernetes control plane.  I was able to use Amazon EKS to set up and run my Kubernetes clusters and integrate Kubernetes with other AWS services.

### One thing I didn't expect

The one thing I didn't expect was the replacement of the terminated EC2 instances.

### This project took me...

This project took me 2 hours. The part that took the longest was adding the access policy. 

---

## What is Kubernetes?

Kubernetes is a container orchestration platform, it coordinates containers so they're running smoothly across all your servers. It makes sure all containers are running where they should, scales containers automatically to meet demand levels, and even restarts containers if something crashes.
Companies and developers use Kubernetes for keeping large, container-based applications steady and easy to scale with traffic.

I used eksctl to create a cluster within my EC2 instance's termninal. The create cluster command I ran defined the node group and the instance type.



I initially ran into two errors while using eksctl. The first one was because eksctl was not installed. The second one was because my EC2 instance didn't have the permission to create an EKS cluster.

![Image](http://learn.nextwork.org/zealous_maroon_serene_raspberry/uploads/aws-compute-eks1_ff9bfc221)

---

## eksctl and CloudFormation

Cloudformation helped create my EKS cluster because eksctl sets up a CloudFormation stack to automate the creation of all the necessary resources for the EKS cluster. It created VPC rescources to make it work for a Kubernetes cluster. eksctl creates a whole new VPC for us to let us start fresh.

There was also a second Cloudformation stack for the note group.  The difference between a cluster and a node group, is that a cluster is made up of nodes and a node group lets you manage your nodes by grouping them together.  

![Image](http://learn.nextwork.org/zealous_maroon_serene_raspberry/uploads/aws-compute-eks1_w3e4r5t6)

---

## The EKS console

I had to create an IAM access entry in order to be able to see and control all parts of my EKS cluster, including all the nodes inside. An access entry connects AWS IAM users with Kubernetes’ Role-Based Access Control (RBAC), which is Kubernetes' system to manage access inside a cluster. I set up the access entry under IAM Principal, by selecting my IAM user's ARN and making sure my IAM Admin's name at the top right corner matched my ARN.  

It took me 2 hours to create my cluster. Since I'll create this cluster again in the next projext of this series, this process would be sped up if I didn't miss the add policy button when I initially tried to add the access policy.

