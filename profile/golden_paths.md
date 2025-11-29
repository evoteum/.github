# Golden Paths

![img.png](yellow_brick_road.png)

Golden Paths are the practical expression of Evoteum’s **automation-first** philosophy.  
They represent the paved, automated routes that make software delivery **safe, fast, and reliable**.  

A Golden Path is not the only way to build and run software. In organizations with strong, interdisciplinary teams, it can be appropriate to let a team deploy their application in their own way.  
They have the skills and context to make informed choices, and sometimes innovation emerges from these experiments.  

However, efficiency matters. It is usually better to have **one team invent the wheel once** than to have **many teams reinvent it many different ways**.  
Golden Paths strike this balance: they give most teams a proven, supported way forward, while still leaving room for occasional divergence when truly necessary.

By standardizing common workflows, Golden Paths reduce cognitive load for developers and allow teams to focus on delivering business value, making them **recommended, low-friction way** to put code in front of customers.  

In this document, we present two contrasting Golden Paths:  
- 🟧 **Orange Path**: an AWS-first approach using Terraform, ECS, and GitHub Actions.  
- 🟦 **Blue Path**: a Kubernetes-native approach using Crossplane, Kubernetes, and ArgoCD.  

Both paths solve the same problem in different ways. Together, they highlight the trade-offs between **vendor-managed simplicity** and **open-source flexibility**.

## 🟧 The Orange Path: AWS Golden Path
- Infrastructure defined in **Terraform**  
- Applications deployed on **AWS ECS**  
- CI/CD pipelines in **GitHub Actions**  
- Deploys using a single OpenTofu module.
- Represents today’s **mainstream AWS-first stack**, stable and widely used.

👉 Explore the Orange Path in [Planzoco](https://github.com/evoteum/planzoco)


## 🟦 The Blue Path: Kubernetes Golden Path
- Infrastructure provisioned via **Crossplane**  
- Applications deployed on **Kubernetes**  
- GitOps workflows powered by **ArgoCD**  
- Deploys using an `app.yml` file.
- Represents tomorrow’s **Kubernetes-native approach**, portable and declarative.  

👉 We are currently building the blue path!


## ⚖️ Why Both Paths?

In production, a **single standard Golden Path** is always preferable:  
- Reduces cognitive load for developers  
- Simplifies operations  
- Avoids drift across multiple competing approaches  

So why did we build two?  

To demonstrate that there are **multiple valid ways** to achieve the same goal of delivering applications reliably:

- The **Orange Path** shows what’s possible by staying within a single vendor ecosystem, using AWS-native services like ECS alongside Terraform and GitHub Actions.  
- The **Blue Path** shows how leaning into open source and Kubernetes-native tooling (Crossplane + ArgoCD) provides the same outcomes with greater flexibility and portability.

If we had to choose, our preference is the **Blue Path**:  
- Kubernetes can run anywhere; cloud, on-prem, or hybrid.  
- Crossplane ensures infrastructure remains in a declared, reconciled state.  
- This combination enables a consistent platform experience without vendor lock-in.  

That said, **Kubernetes is a hungry beast**. Unless an organization is leaning hard into the K8s ecosystem with tools like Crossplane, it can be overkill:  
- Running clusters adds operational complexity and cost.  
- For many teams, **ECS is cheaper and easier** to adopt while still delivering reliable results.  

Both paths are valid; the right choice depends on the maturity, scale, ambitions of the organization...  
**and how much you want your life to be run by YAML 😄**


## 🔍 Orange vs Blue Path Comparison

| Aspect              | 🟧 Orange Path                                                             | 🟦 Blue Path                                                    |
|---------------------|-------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| Infra Definition    | Terraform                                                                                 | Crossplane (Kubernetes-native)                                                |
| Platform            | AWS ECS                                                                                   | Kubernetes                                                                    |
| Delivery Model      | CI/CD via GitHub Actions                                                                  | GitOps via ArgoCD                                                             |
| Ecosystem           | AWS-native, vendor-managed                                                                | Open-source, cloud-agnostic                                                   |
| Complexity          | Lower (managed services)                                                                  | Higher (K8s ops overhead)                                                     |
| Cost                | Often cheaper, fewer moving parts                                                         | Higher baseline (clusters, controllers)                                       |
| Portability         | Limited to AWS                                                                            | Runs anywhere Kubernetes runs                                                 |
| Drift Management    | Detects drift only at `plan/apply` time. Continuous reconciliation requires wrapping Terraform in a cron job or pipeline. | Continuous reconciliation built-in (controllers watch & enforce declared state). |
| Best Fit For        | Teams seeking simplicity, AWS-first alignment                                             | Teams leaning into K8s and open-source platforms                              |

