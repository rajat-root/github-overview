---
title: "Declarative vs. Imperative in IaC (Infrastructure as Code)"
author: "Your Name"
date: "January 15, 2025"
revealOptions:
  controls: true
  progress: true
  slideNumber: true
  transition: "fade"
---

# Declarative vs. Imperative
<!-- end_slide -->

---

## Agenda

1. **What is meant by Declarative and Imperative?**
2. **Basic Infrastructure-as-Code Example**
3. **Declarative Approach**
4. **Imperative Approach**
5. **Key Differences**
6. **Pets vs Cattle (Preview)**
<!-- end_slide -->

---

## What is meant by Declarative and Imperative?

- **Programming Paradigms**: Different ways of telling the computer what to do
  - Imperative
  - Declarative
  - Functional
  - Structured
  - Object-Oriented
- **Focus for IaC**: Two main paradigms for Infrastructure as Code (IaC):
  1. **Declarative** – Define the desired end state
  2. **Imperative** – Define the exact steps to achieve the end state

<!-- end_slide -->

---

## Basic Infrastructure-as-Code Project

**Example**: Deploying a single virtual machine (VM) in Microsoft Azure

**Components**:
- **Resource Group** (`rg-iac-example-uks-001`)
- **Virtual Network** (`vnet-iac-example-uks-001`)
- **Subnet** (`snet-iac-example-uks-001`)
- **Network Security Group** (`nsg-iac-example-uks-001`)
- **Network Interface** (`nic-iac-example-uks-001`)
- **Public IP Address** (`pip-iac-example-uks-001`)
- **Virtual Machine** (`vm-iac-example-uks-001`)
<!-- end_slide -->

---

## Declarative Approach

- **Definition**: Focus on the **end state** rather than the process.
- **Example**:
  - A declarative tool (e.g., Puppet, Terraform) simply knows:
    > “I want this resource group, virtual network, subnet, NSG, NIC, PIP, and VM created.”
  - The tool decides the order in which resources are deployed (unless additional resource-awareness features are used).
<!-- end_slide -->

---

## Declarative Example: Eventual Consistency

1. Tool attempts to deploy in a certain order (e.g., VNet → RG → NSG → …).
2. Some resources fail if their dependencies are not ready yet.
3. After several executions:
   - **Deployment 1**: Fails on VNet (RG not ready), but RG is successfully created.
   - **Deployment 2**: VNet, Subnet succeed; NSG fails because Subnet is still deploying, etc.
   - **Deployment 3**: All remaining resources succeed.
4. **End state** is eventually correct, but intermediate steps may fail.

**Key Term**: *Eventual Consistency*
- Resource dependencies are resolved after multiple runs.

<!-- end_slide -->

---

## Imperative Approach

- **Definition**: You define **exactly** how to get to the end state, in the correct order.
- **Example** order for Azure deployment might be:
  1. Resource Group
  2. Virtual Network
  3. Subnet
  4. Network Security Group
  5. Network Interface
  6. Public IP Address
  7. Virtual Machine

- **Pros**:
  - If you know the correct order, it often works the first time.
- **Cons**:
  - Requires more knowledge and upfront effort to figure out all dependencies and steps.

<!-- end_slide -->

---

## Key Differences

| **Declarative**                       | **Imperative**                     |
|--------------------------------------|------------------------------------|
| Define **what** the final state is   | Define **how** to achieve the goal |
| Order of tasks often auto-determined | Order of tasks is explicitly set   |
| May require multiple runs            | Typically works in one go (if correct) |
| Great for large-scale, consistent infrastructure | Useful when explicit control is needed |

<!-- end_slide -->

---

## Pets vs. Cattle (Preview)

- **Pets**:
  - Individually managed, unique, carefully tended.
- **Cattle**:
  - Large number of identical resources, destroyed/replaced as needed.

In IaC, we lean toward treating servers as **cattle**, not **pets**.

<!-- end_slide -->

---

## Conclusion

- **Declarative**: Describe your desired state; let the tool figure it out.
- **Imperative**: Spell out each step to get to your final state.
- Both approaches are valuable in **Infrastructure as Code**.
- It’s essential to understand which paradigm fits best for your project’s needs.

**Next Steps**:
- Dive deeper into examples with Ansible (imperative aspects) and Terraform (declarative aspects).
- Explore “pets vs. cattle” approach to building highly scalable, fault-tolerant systems.

<!-- end_slide -->

---

