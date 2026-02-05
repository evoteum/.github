# evoteum
```shell
ideas to impact
```

Welcome to **evoteum**!

## What is evoteum?

Evoteum brings modern platform engineering principles to life through open source, reproducible systems.

## Engineering Philosophy

We believe in,
- openness
- everything as code
- behaviour driven development

[Learn more...](engineering_philosophy.md)

### Key Projects

These projects show how we apply our engineering philosophy to create business value.

For optional deeper technical write-ups of selected projects, see [portfolio](portfolio.md).

### Evoteum Metal Kubernetes Lab

[evoteum/kubernetes-lab](https://github.com/evoteum/kubernetes-lab) | _Kubernetes (multi-architecture), Ansible, ArgoCD, HAProxy, Keepalived, Helm, Cilium_

- Pain:
  - Setting up Kubernetes on your own hardware is difficult
- Solution:
  - Ansible Playbook that installs everything necessary on top of the Operating System, with a clean handoff to ArgoCD.
  - Ansible Playbook that reverts all changes, providing for clean cluster rebuild.

A fully automated Kubernetes cluster builder for physical servers.

### Drydock (in development)

[evoteum/drydock](https://github.com/evoteum/drydock) | _Tinkerbell, Kubernetes-native provisioning, Go, PXE_

- Pain:
  - Setting up Kubernetes on your own hardware is difficult
  - Current provisioning tools assume an operating system is available
  - Current hardware management tools are not Kubernetes native and assume that PXE infrastructure is already in place.
- Solution:
  - Fully automated system to turn empty servers into a Kubernetes cluster in one click, without manual operating system installation. 

A Kubernetes native bare metal provisioning and management system for creating clusters from empty hosts.

### GitHub Estate Manager
[evoteum/estate-repos](https://github.com/evoteum/estate-repos) | _Terraform, GitHub Actions CI/CD_

- Pain:
  - Manually ensuring that all GitHub repositories are set up with the correct settings quickly becomes impossible.
  - Manually setting up CI/CD within a polyrepo estate is a time drain.
  - Manually creating artifact repositories for each repository is annoying.
- Solution:
  - Fully automated system to turn repos.yml into the repository catalogue 

A declarative GitHub and Quay estate manager driven by a single repos.yml.


### Planzoco
[evoteum/planzoco](https://github.com/evoteum/planzoco) | _Go, Terraform, AWS ECS, GitHub Actions CI/CD_

- Pain:
  - Coordinating a group of friends or family is hard.
- Solution:
  - A system that lets coordinators ask questions and lets participants answer and vote on all responses.

A group event coordination system built using our [orange Golden Path](golden_paths.md).


### It's Beginning to Look a Lot Like Christmas
[itsbeginningtolookalotlike.christmas](https://itsbeginningtolookalotlike.christmas) | Python, Terraform, GitHub Actions_

- Pain:
  - It is hard to define success metrics, then surface them for observability.
  - "Christmasyness" is an emotional, subjective concept that is hard to measure consistently.
- Solution:
  - Use the popularity of "It is Beginning to Look a Lot Like Christmas" as a measurable proxy and graph it automatically using GitHub Actions.

A fully automated GitHub Actions data pipeline that pulls data, updates the site and graphs the onset of Christmas.


### TOCGEN
[evoteum/tocgen](https://github.com/evoteum/tocgen) | _Python, Docker, GitHub Actions CI/CD_

- Pain:
  - Managing README table of contents sections manually is annoying.
- Solution:
  - Python application to update the table of contents automatically.

A Markdown Table of Contents generator that updates documentation automatically.
