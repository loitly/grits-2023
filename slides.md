---
title: Exploring IRSA Kubernetes
theme: sky
revealOptions:
  transition: 'zoom'
---

#### Introduction to IRSA Kubernetes

![](img/cluster.png)

---

#### Design Objectives

- Multiple tenants
- Multiple projects
- Variety of environments
- Deployments from Firefly, IRSA UI, and IRSA Data System
- Environments: test, ops, and internal ops

---
#### Cluster Overview
<div style="text-align:left"> 
<p>OPS Cluster</p>
</div>
<img src="img/payload.png" style="height:300px"/>
<img src="img/cap.png" style="height:300px"/>

<div style="text-align:left">
<p>DEV Cluster</p>
 <li> Dynamic deployments
 <li> Multiple instances at different commit points
</div>
<!-- .element: class="fragment" -->

---

#### Maintenance

- Regular maintenance on the host machines
- Complete update of Kubernetes software stack
  - Every 6 months (incremental updates)
  - Docker: Container runtime
  - kubeadm: tool used to build Kubernetes clusters
  - Weave Net: Container Network Interface (CNI)
  - Ingress controller
- Kubernetes cordon

---


#### Monitoring Tools

<img src="img/prom-graf.png" style="height:300px"/>
<img src="img/grafana.png" style="height:300px"/>

- Zabbix and Xymon
- Prometheus
- Grafana
- Slack notification
- Dashboards


---

#### Automation

<p>
Typical GitOPS workflow
</p>


![](img/opsflow.png)

---

#### Our Deployment Process

![](img/opsflow-our.png)

- Manual execution of Jenkins pipeline
- Publishing chart to local Helm Chart Repository


---

#### What is irsajenkins

- Containerized and managed as code in Git
  - Plugins and configuration built into the image
- Support Docker/Compose (build/publish)
  - Isolation, consistency, portability
- Support Helm (create/publish)
- Automatically build and test on merge
- Slack notification

---

#### What is Argo CD

<p>
Automated GitOps tool for managing and deploying Kubernetes applications.
It aligns your cluster with Git-based declaratively-defined infrastructure, effectively automating application deployment.
</p>

![](img/argo.png)

---

#### Argo CD Dashboard

![](img/argocd.png)

---

#### Argo CD Application

![](img/argocd-app.png)

- Force Sync
- Update Kubernetes manifest
- View application logs

---

#### Conclusion
<p>
In summary, IRSA Kubernetes offers a robust solution for managing complex deployments across different environments.
We have firsthand positive experiences with the platform and that's why we're here to share our insights and knowledge with you today.
Thank You!
</p>

Any questions?