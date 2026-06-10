# Azure-Cloud-Setup-Project
Foundational Azure setup and deployment.
Here is the fully populated `README.md` document, drafted with the requisite academic rigor and technical precision to satisfy the evaluation criteria.

Copy the text block below in its entirety and paste it directly into your GitHub repository's editor.

---

# Azure Free Tier Account Setup & Governance Guide

## 1. Project Overview

This document outlines the foundational setup, configuration, and governance of a Microsoft Azure cloud environment. It serves as a comprehensive guide covering account creation, portal navigation, resource deployment, and fiscal management. The infrastructure modeled in this deployment is specifically architected to provide a baseline environment for data analysis, econometric modeling, and technical administration while maintaining strict adherence to zero-cost guardrails.

## 2. Account Creation & Verification Process

The initial provisioning of the Azure environment required establishing a verified Microsoft identity. Registration was executed via the Azure portal (azure.microsoft.com). To satisfy Microsoft's security and anti-fraud protocols, a dual-verification methodology was required: primary identity verification via an active phone number, and secondary verification via a valid credit card. The credit card functions strictly for authorization holds to prevent automated creation of fraudulent compute resources and is not charged during the Free Tier lifecycle unless explicit usage limits are exceeded.

## 3. Azure Portal Navigation & Customization

The Azure Portal utilizes a resource-centric navigation model. Key services are accessed via the global search bar or the left-hand navigation pane.

* **Dashboard Customization:** To optimize the monitoring of active resources and accrued costs, a custom dashboard was implemented. This centralized interface was customized by deploying the **Resource groups** tile to track active infrastructure and the **Cost Management** tile to provide immediate, high-level visibility into billing telemetry the moment the portal is accessed.

## 4. Free Tier Limits & Resource Quotas

Maintaining strict fiscal discipline necessitates a precise understanding of Azure Free Tier constraints.

* **Initial Credit:** Newly provisioned accounts receive a standard $200 USD credit, valid for the initial 30-day period, intended for the exploration of premium enterprise services.
* **12-Month Services:** Specific compute and storage resources remain free for the first 12 months. Notably, this includes 750 hours per month of burstable B-series Virtual Machines (e.g., `Standard_B1s`) and specific allocations of Standard Managed Disks.
* **Always Free:** A subset of services, such as the Azure App Service (F1 tier) and specific outbound data transfer limits, remain perpetually free regardless of the account lifecycle stage.

## 5. Security & Identity Management

Securing the cloud environment is paramount under the cloud computing Shared Responsibility Model.

* **Multi-Factor Authentication (MFA):** MFA provides a critical layer of defense against credential compromise. Within this environment, MFA is enforced globally via Microsoft Entra ID by activating "Security Defaults," which mandates secondary verification for all administrative access.
* **Best Practices:** All future deployments and user assignments will adhere to Role-Based Access Control (RBAC), ensuring that the principle of least privilege is maintained across all logical containers.

## 6. Resource Deployment Strategy

To test infrastructure provisioning, a logical container designated `RG-DataAnalysis-01` was established. Within this Resource Group, a Linux-based Virtual Machine (`VM-DataAnalysis-01` running Ubuntu Server) was deployed utilizing the Free Tier eligible `Standard_B1s` size.

* **Geographic Optimization:** The resources were deployed exclusively within the **South Africa North** region. This datacenter selection minimizes network latency and optimizes data packet routing for operations executing from West Africa.
* **Operational Use Case:** The Linux environment provides a robust command-line interface, establishing an optimal foundational environment for executing data manipulation scripts, managing databases, and learning Linux system administration without incurring Windows licensing overhead.

## 7. Cost Management & Billing Alerts

To ensure absolute control over potential financial exposure on a Pay-As-You-Go subscription, rigid budget guardrails were configured.

* **Budget Configuration:** A localized budget was established within the Cost Management + Billing module.
* **Alert Thresholds:** An automated email trigger was bound to this budget, specifically configured to execute an alert when consumption reaches **75%** of the defined threshold. This provides sufficient lead time to audit the environment, identify anomalous compute usage, and terminate running resources before actual debt is incurred.

## 8. Completion Checklist & Troubleshooting

* [x] Account Registration & Identity Verification
* [x] Resource Group & Compute Deployment
* [x] Custom Dashboard Configuration (Resource & Cost Tiles)
* [x] 75% Budget Alert Implementation
* [x] Security & MFA Documentation
* **Support Resources:** Microsoft Learn Documentation, Azure Cost Management Analytics.
