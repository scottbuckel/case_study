# SRE Case Study: Multi-Region Expansion for BlockChain Solutions Inc.

This repository contains my response to the SRE Case Study provided by BlockChain Solutions Inc. The case study was sent to me at 9 AM, and this is my immediate response, sent 4 hours later.

## Files

* `SRE Case Study.pdf`: The original case study document outlining the problem statement and requirements.
* `CaseStudyResponse.pdf`: My detailed solution and approach in PDF format.
* `CaseStudyResponse.pptx`: My detailed solution and approach in PowerPoint presentation format.

---

## Case Study Instructions

This document outlines a case study that will serve as the foundation for our discussion during your technical interview. Please come prepared to discuss your solution by bringing either a slide deck or a document that details your approach.

The aim is to think clearly through your solution and for us to take a collaborative approach to problem-solving.

---

## Problem Statement

You’re an engineer at “BlockChain Solutions Inc.”, a rapidly growing company specializing in blockchain technology. We host and maintain a variety of Substrate-based nodes and other types of stateful and stateless services that underpin our platform. To date, all infrastructure has been located in a single AWS region, `eu-west-1`.

As we expand our user base and strive for greater reliability, we need to expand our footprint to a US region to maintain a good experience and ensure our systems are bulletproof.

### Current Architecture

Some key aspects from our current layout:

* All infrastructure is managed using **Terraform**. Our Terraform code resides in a single repository. While CI workflows are configured to run `terraform plan` on changes, `terraform apply` is executed manually by engineers.
* Workloads are containerized and deployed to **Amazon EKS**.
* For select critical services, we maintain both an **active and a dormant instance**. Both are kept in sync, but **failover between them is a manual process**.
* All source code is stored in **GitHub**, in a mix of public and private repositories.
* Our application deployment process uses **Helm charts**, stored within their respective code repositories. CI scripts are used to deploy these into EKS, providing minimal automation.
* Observability is handled via a **Grafana stack**.

---

## The Task

We want to expand our infrastructure into US regions to enhance the production readiness of our services. As a Senior SRE, you are responsible for designing and implementing the necessary changes.

### Requirements to be Addressed

* HTTP-based services must be **globally accessible**.
* Any architecture must be **scalable** to accommodate future expansion into additional regions.
* The design must account for **Disaster Recovery** and ensure resilience against various failure scenarios.
* Given that this is our first expansion, we need to ensure **infrastructure stability and consistency**. This includes considering any tools or processes we should implement.
* Consider the implications of this expansion on supporting services, including **networking, monitoring, cost, and SLOs/SLIs**.
* Outline any **trade-offs or potential concerns** associated with your proposal.

Elaborate on how your proposed architecture will support these objectives, and detail any special tools or processes you would introduce to ensure a smooth execution and ongoing stability.