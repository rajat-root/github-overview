---
theme:
  override:
    code:
      alignment: left
      background: false
---

# Declarative vs. Imperative

<!-- end_slide -->

## Agenda

1. **What is meant by Declarative and Imperative?**  
2. **Basic Infrastructure-as-Code Example**  
3. **Declarative Approach**  
4. **Imperative Approach**  
5. **Key Differences**  
6. **Pets vs. Cattle (Preview)**

<!-- end_slide -->

## What is meant by Declarative and Imperative?

- **Programming Paradigms**: Different ways of telling the computer what to do.  
  - Imperative  
  - Declarative  
  - Functional  
  - Structured  
  - Object-Oriented  

- **Focus for IaC**: Two main paradigms for Infrastructure as Code (IaC):  
  1. **Declarative** – Define the desired end state.  
  2. **Imperative** – Define the exact steps to achieve the end state.

<!-- end_slide -->

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

## Declarative Approach

- **Definition**: Focus on the **end state** rather than the process.  
- **Example**:
  - A declarative tool (e.g., Puppet, Terraform) is given instructions akin to:
    “I want this resource group, virtual network, subnet, NSG, NIC, PIP, and VM created.”
  - The tool decides the order in which resources are deployed (unless further constraints or resource-awareness features are specified).

<!-- end_slide -->

## Declarative Example: Eventual Consistency

1. The tool attempts to deploy in a certain order (e.g., **Resource Group** → **Virtual Network** → **Subnet** → **NSG**, etc.).  
2. Some resources fail if dependencies are not yet ready.  
3. After several executions:
   - **Deployment 1**: Fails on the Virtual Network (RG not ready), but successfully creates the Resource Group.  
   - **Deployment 2**: Virtual Network and Subnet succeed; NSG fails because the Subnet is still deploying, etc.  
   - **Deployment 3**: All remaining resources succeed.  
4. The **end state** is eventually correct, even though intermediate steps may fail.

**Key Term**: *Eventual Consistency*  
- Resource dependencies are fully resolved after multiple runs.

<!-- end_slide -->

## Imperative Approach

- **Definition**: You define **exactly** how to reach the end state, in the correct order.  
- **Example** order for an Azure deployment might be:
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
  - Requires more knowledge and effort up front to determine all dependencies and steps.

<!-- end_slide -->

## Key Differences

| **Declarative**                                | **Imperative**                                |
|------------------------------------------------|-----------------------------------------------|
| Define **what** the final state should be      | Define **how** to achieve the goal            |
| Order of tasks often auto-determined           | Order of tasks is explicitly set              |
| May require multiple runs to reach consistency | Typically works in one go (if the order is correct) |
| Great for large-scale, consistent infrastructure | Useful when explicit control is needed       |

<!-- end_slide -->

## Pets vs. Cattle (Preview)

- **Pets**:  
  - Individually managed, unique, and carefully tended.  
- **Cattle**:  
  - Large numbers of identical resources, destroyed or replaced as needed.  

In IaC, we lean toward treating servers as **cattle**, not **pets**.

<!-- end_slide -->

## Conclusion

- **Declarative**: Describe your desired state; let the tool figure it out.  
- **Imperative**: Spell out each step to get to the final state.  
- Both approaches are valuable in **Infrastructure as Code**.  
- It’s essential to understand which paradigm fits your project’s needs.

**Next Steps**:
- Dive deeper into examples with Ansible (imperative aspects) and Terraform (declarative aspects).  
- Explore the “pets vs. cattle” approach to building highly scalable, fault-tolerant systems.

<!-- end_slide -->
