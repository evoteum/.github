# Portfolio

This document provides deeper technical detail on the aforementioned projects. All code is available on GitHub.

These projects reflect a consistent approach to infrastructure and tooling: treating systems as declarative, reproducible, and safe to change; favouring reconciliation over manual intervention; and designing for long-lived, unattended operation. The focus is less on individual technologies and more on system behaviour, lifecycle management, and operational clarity.


## Evoteum Metal Kubernetes Lab

https://github.com/evoteum/kubernetes-lab 

_Kubernetes (multi-architecture), Ansible, ArgoCD, HAProxy, Keepalived, Helm, Cilium_

Designed and built a fully automated, highly available Kubernetes platform running on bare metal, using Ansible to orchestrate the entire cluster lifecycle from bootstrap to GitOps handover. Implemented HA control plane provisioning with HAProxy and Keepalived VIP failover, automated node join and cluster upgrades via kubeadm, and established a fully declarative add-on system using Helm and ArgoCD App-of-Apps. The project delivers a production-grade, reproducible multi-architecture cluster with zero manual post-install steps and complete Everything-as-Code principles.

- HA control plane using HAProxy and Keepalived
- Multi-architecture node support
- Automated join, upgrade and add-on lifecycle via kubeadm, Helm and ArgoCD
- Zero manual post-install steps and complete Everything-as-Code reproducibility


## Drydock (in development)

https://github.com/evoteum/drydock

_Tinkerbell, Kubernetes-native provisioning, Go, PXE_

Drydock is a Kubernetes-native, end-to-end bare metal provisioning system designed to convert unprovisioned hosts into a fully functional, highly available Kubernetes cluster with minimal human involvement. It owns a dedicated provisioning VLAN, controls DHCP and PXE boot, loads hosts into SunshineOS for hardware discovery, generates Tinkerbell hardware manifests and executes immutable provisioning workflows to build the cluster.

Once deployed, the Drydock Operator provides continuous reconciliation: detecting new hardware, provisioning nodes automatically, and removing absent nodes to maintain cluster consistency. Destroy flows use HerculesOS to securely wipe machines and enable clean rebuilds. Designed for both enterprise servers and low-power devices, Drydock aims to deliver predictable, cloud-like lifecycle management for physical infrastructure with a single declarative command.

Key capabilities:

- PXE boot into SunshineOS for hardware discovery
- Automatic generation of Tinkerbell hardware manifests
- Immutable image provisioning workflows
- A reconciliation operator that continuously provisions and retires nodes
- Secure machine wipe and rebuild via HerculesOS
- Designed for both enterprise servers and low-power hardware
- Aims for full automation from "plug in the machine" to "GitOps-managed cluster"

## GitHub Estate Manager

https://github.com/evoteum/estate-repos

_Terraform, GitHub Actions CI/CD_

Built a GitHub and Quay estate management system that treats a single repos.yml as the source of truth for all repositories. OpenTofu modules reconcile each entry into an idempotent set of GitHub repositories, repository settings, templated standard README, reusable GitHub Actions workflows and repository-scoped variables, as well as matching Quay container registries for build artefacts. This removed manual repo setup, enforced consistent defaults and made onboarding new services as simple as adding one YAML block.

Key capabilities:

- A single repos.yml acts as the source of truth
- OpenTofu modules reconcile repositories, settings, permissions and registry definitions
- Generates consistent README templates, reusable workflows and repository variables
- Eliminates manual setup and enforces organisation-wide defaults
- Adding a new service becomes a single YAML entry


## Planzoco
https://github.com/evoteum/planzoco

_Go, Terraform, AWS ECS, GitHub Actions CI/CD_

A production-ready Golden Path example for containerised services.

- Coordinating friends and family is hard. Planzoco allows you to ask questions, such as, "Where are we going?" and "What date works best?" and allows participants to both answer, and vote on those answers.
- Developed Go microservice, containerised and deployed via the IaC pipeline.
- Created a Golden Path deployment framework: Delivered an opinionated, production-ready ECS model applicable to all organisation repos, embedding security and minimising setup friction.
- Authored composable Terraform modules for ECS, ALB, IAM, VPC networking, and ACM, enabling rapid, consistent environment provisioning.
- Automated DNS management with ACM + Cloudflare Terraform 
- Reusable modules applicable across the entire organisation

## It's Beginning to Look a Lot Like Christmas

https://itsbeginningtolookalotlike.christmas

_Python, Terraform, GitHub Actions, GitHub Pages_

A fully automated GitHub Actions data pipeline.

- Python service that queries the Spotify API daily
- GitHub Actions schedules and deploys updates
- Zero maintenance since 2024-11-01
- Demonstrates event-driven automation, observability and Everything-as-Code principles

...also, delightfully silly...

## TOCGEN

https://github.com/evoteum/tocgen

_Python, Docker, GitHub Actions CI/CD_

A fully automated Markdown Table of Contents generator designed to eliminate manual editing across multi-repository estates. The tool scans Markdown files for declarative TOC markers, detects headings, and inserts a consistently formatted Table of Contents based on configurable rules. It supports local execution, containerised usage, and GitHub Actions integration. Designed to enforce predictable, accessible documentation across an organisation, tocgen demonstrates strong DevEx thinking, declarative tooling, and automated standards enforcement within GitHub-native workflows.

Key features include:

- Automatic discovery of all Markdown files in a repository containing TOC markers, reducing maintenance effort and ensuring consistency.
- Flexible configuration through both CLI flags and a .tocgen.yml file, enabling Everything-as-Code management of documentation structure.
- Robust TOC generation pipeline that ignores code blocks, handles Markdown and HTML comment markers, and preserves repository-specific formatting requirements.
- Support for ordered or unordered list styles, custom indentation, heading level control, and custom marker strings.
- End-to-end CI integration via a reusable GitHub Action, allowing documentation to self-update on every push without human intervention.
- Docker packaging for reproducible, environment-agnostic execution.
