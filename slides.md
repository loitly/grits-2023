---
title: Exploring IRSA Kubernetes
theme: sky
revealOptions:
  transition: 'zoom'
---


### Exploring IRSA Kubernetes

Note: Share our experiences we have while operating Kubernetes in production

Other enhancements we’ve added to make it even better.

---


#### What is IRSA Kubernetes

![](img/cluster.png)


Note: On premise kubernetes cluster


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


Note: able to see and test the changes
before they are merged.

Esp useful for UI team

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

Notes:
<font size=-1>
Prometheus is an open-source software designed to provide monitoring and alerting functionality for 
cloud-native environments, including Kubernetes. It collects and stores time series data

Grafana is an open source interactive data-visualization tools which allow users 
to see their data via charts and graphs
</font>

---

#### Automation

<p>
Typical GitOPS workflow
</p>


![](img/opsflow.png)

Notes: 
Kubernetes allow us to adopt modern workflow

Trigger release by merging a branch
or, advancing a tag.

---

#### Our Release Process

![](img/opsflow-our.png)

- Manual execution of Jenkins pipeline
- Publishing chart to local Helm Chart Repository


Notes:

Can also use Helm CLI to manage application deployment independent of the workflow.    

Drill down into a couple of these components to provide more details

---

#### What is irsajenkins

- Containerized and managed as code in Git
  - Plugins and configuration built into the image
- Support Docker/Compose (build/publish)
  - Isolation, consistency, portability
- Support Helm (create/publish)
- Automatically build and test on merge
- Slack notification

Notes:
Helm provide clean separation between build and deployment

---

#### What is Argo CD

<p>
Automated GitOps tool for managing and deploying Kubernetes applications.
It aligns your cluster with Git-based declaratively-defined infrastructure, effectively automating application deployment.
</p>

![](img/argo.png)

Notes:
Another major addition to our workflow

---

#### Argo CD Dashboard

![](img/argocd.png)

---

#### Argo CD Application

![](img/argocd-app.png)

- Force Sync
- Update Kubernetes manifest
- View application logs

Notes:
Access control.  No need to pass along kubeconfig.

Dynamic updates; scaling

---

#### Conclusion
<p>
In summary, IRSA Kubernetes offers a robust solution for managing complex deployments across different environments.
We have firsthand positive experiences with the platform and that's why we're here to share our insights and knowledge with you today.
Thank You!
</p>

Any questions?


<style>
  p {
      font-style: italic;
      font-size: large;
  }
  
  .reveal h4 {
      text-transform: unset;
  }
</style>