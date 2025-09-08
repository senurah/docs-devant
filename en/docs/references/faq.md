# Frequently Asked Questions

## General

### Q: What is Devant?
Devant is a powerful IPaaS with first-class AI support. Incorporate AI agents into the integrations you build in low-code and pro-code, and move away from siloed systems to intelligent digital experiences with Devant by WSO2—the AI iPaaS that your AI Agents can call “home”.

### Q: What is an organization in Devant?
An organization is a logical grouping of users and their resources. It may represent a company, community, or a single user. Users can belong to multiple organizations, and each organization can have different roles assigned to its users to control access to Devant features.

### Q: What is a project in Devant?
A project is a logical grouping of related integrations to help you organize your work. Each project provides runtime isolation through namespaces when you deploy integrations.

### Q: What is an integration in Devant?
An integration in Devant is a solution that connects systems, automates processes, or exposes functionality. Integrations can take many forms, such as automations, AI agents, APIs, event-driven flows, or file-based processes.

### Q: What is the difference between an internal and external API?
In Devant, you can publish an API as an internal or an external API. A user or an application can access an external API publicly over the internet, whereas an internal API is only accessible through other integrations within the same organization.

### Q: What is a connector in Devant Marketplace?
A connector is a reusable WSO2 Integrator package that simplifies connecting to external or internal systems and APIs, such as Salesforce, SAP, GitHub, and Twilio. You can use the connectors available in the Devant marketplace to implement your integration use cases. Connectors can be created and published by both WSO2 and Devant users.

### Q: What is a trigger in Devant Marketplace?
A trigger is a construct that enables users to receive known event payloads from external systems, facilitating event-driven programming.

### Q: What is a sample/template in Devant?
A sample or template is a prebuilt WSO2 Integrator program that covers a popular integration use case or pattern. Examples include connecting Salesforce to Slack or implementing content-based routing.

### Q: What are the support options in Devant?
You can find information about our support plans, including `free`, `basic`, and `enterprise` options at https://wso2.com/saas-support-plans/.

### Q: How can I perform log monitoring or analytics for the Azure environment?
If you have a log monitoring product or service, such as Azure Monitor, you can use it together with Devant. Note: The log monitoring tool is not included in the infrastructure cost.

### Q: What is the maximum request payload size supported by Devant?
Devant allows a maximum request payload size of 50 MB.

### Q: What source control software does Devant support?
Devant now supports GitHub, Bitbucket and GitLab.

### Q: Why don't I see the undeployed builds for my integration in Devant?
You are allowed to build your integration any number of times. However, Devant has a limit on retaining undeployed builds. For users on the free-tier, Devant will retain **only one** undeployed build. For those on any other tier, Devant will retain the **latest five** undeployed builds.

### Q: What is WSO2 Integrator?
WSO2 Integrator is a 100% open-source, AI-native integration platform built for the cloud. It helps you connect any system across your business and tackle integration challenges with ease. By using WSO2 Integrator in Devant, you can accelerate delivery—often 2–3x faster. Learn more at https://wso2.com/integrator/.

### Q: What is Asgardeo?
Asgardeo is an identity provider (IdP) that allows developers to secure access for consumers, business partners, employees, and APIs. Asgardeo is Devant’s default IDP. To learn more, visit https://wso2.com/asgardeo/.

### Q: As a Cloud Data Plane user, how can I create integrations in multiple data planes?
When an organization admin onboards a new organization in Devant, they can choose the preferred data plane. Devant then sets the selected data plane as the default for the entire organization. Subsequently, users within the free tier of the cloud data plane can create integrations only in the set default data plane. If a free-tier user needs to create integrations in a different data plane, the user must get a paid subscription.

## Security and data protection

### Q: How is data managed in Devant?
Devant manages data using WSO2 containers and Kubernetes clusters, which provide scalability, resilience, and security. Find out more [here](https://wso2.cachefly.net/wso2/sites/all/trust/wso2-public-cloud-data-protection-faq.pdf).

### Q: What is the WSO2 Subprocessor list?
This is a detailed list of all subprocessors used by WSO2, including their name, location, and purpose. This information is updated frequently to ensure compliance with data protection regulations and is found [here](https://wso2.cachefly.net/wso2/sites/all/trust/wso2-public-cloud-subprocessor-list.pdf).

### Q: How do we secure WSO2 Private and Public Clouds?
WSO2 uses a range of security controls and design patterns to protect against several threats, including internal attacks, software supply chain attacks, service and platform attacks, and more. For more details, see [Cloud Security Process](https://security.docs.wso2.com/en/latest/security-processes/cloud-security-process/).

### Q: How can I connect a Devant integration with a protected third-party application?
To connect a Devant integration with a third-party application, it is necessary to establish seamless communication between the integration and the protected third-party application, especially when connecting to external databases like MySQL, MSSQL, PGSQL, Oracle DB, etc.
To ensure this, the requests coming from the Devant data plane must be allowed by adding the specific data plane IP ranges to your allowlist.

**If your primary region is US:**

- Devant US data plane: `20.22.170.144/28`
- Devant EU data plane: `20.166.183.112/28`

**If your primary region is EU:**

- Devant EU data plane: `54.170.135.118, 52.215.28.29`

## Data planes

### Q: What is a Devant control plane?
The Devant control plane is a centralized management component that oversees and coordinates the workloads deployed by customers. It provides a unified point of control and visibility for the organization, allowing administrators to manage, monitor, and orchestrate the organization’s resources efficiently.

### Q: What is a data plane?
A data plane in Devant is a computing environment designed for running customer workloads. These environments are hosted in either a dedicated cloud infrastructure owned by the customer (private data planes) or on public cloud infrastructure owned by WSO2, also known as the Devant data plane.

### Q: Which regions support the Devant data plane(CDP)?
The Devant data plane is currently supported in the US East 2 and North Europe. However, WSO2 is planning to add support for additional regions as needed.

### Q: Which regions support private data planes(PDPs)?
Private data planes can be deployed in any region where Azure and AWS are available and meet the requirements for PDPs.

### Q: If I want to use my Azure AKS instances as the private data plane, what are the minimum requirements I should meet?
We recommend using a minimum of two (2) workload nodes to ensure high availability.

### Q: Are the Devant control plane and data planes highly available? Are they running on multiple clusters?
The Devant control plane and data plane are designed for high availability using Azure components like AKS, MSSQL, ACR, KV, Service Bus, and so on, with a high availability of 99.99%, which allows at least three workload nodes. In the event of a node failure or upgrade, this setup provides reliable failover. WSO2 also has a backup and recovery strategy in place, including continuous restore drills. If you require AKS cluster-level redundancy, we can consider multiple zones. In this case, the cost will include an additional infrastructure cost.

## Environments

### Q: As a Devant cloud data plane user, why can't I create environments?
You can create environments only if you have a paid subscription in Devant. It can be either Pay-as-you-Go (PAYG) or an Enterprise plan.

### Q: I am a Pay-As-You-Go (PAYG) customer using the Devant cloud data plane. How many environments can I create?
You can create up to 5 environments at the organization level, including the existing Development & Production environments by default. If you have projects in both data planes (US & EU), there will be 4 environments already created in total, and you will only be allowed to create one additional environment either in the US or EU data plane.

### Q: I am an Enterprise subscription customer using the Devant private data plane. How many environments do I get?
As an Enterprise subscription customer, the number of environments you can use is **not** limited.  However, the more environments you use, the more resources you will consume in the data plane for the workload you deploy. This may result in higher infrastructure costs for the private data plane.

### Q: As a Devant cloud data plane user, why don’t I see both US & EU data planes in the data plane selector when creating an environment?
You will see both US & EU data planes only if you have a paid subscription and have created projects in both US & EU data planes.

### Q: I am a customer who use Devant in a private data plane. How many environments can I create?
Initially, you will receive the requested number of environments when establishing your private data plane. Subsequently, you can create additional environments as needed.

## Billing and support

### Q: Whom do I reach out to if I have a billing question?
You can reach out to cloud-billing-support@wso2.com or create a support ticket via our support portal.

### Q: What's a Developer plan?
A Developer plan allows you to try out Devant’s capabilities at no cost. It’s ideal for proof of concept (PoC) tasks or workloads with limited transactions. This plan allows you to experiment with up to 5 integrations and provides US$1,000/year of Devant data plane (CDP) credits.

### Q: How do I calculate the infrastructure costs?
Calculating infrastructure costs depends on the type of workload you want to manage. Here are a few examples:

- **Example 1**: Creating, deploying, and managing a new Integration as an API within Devant; pay for 1 x integration + infrastructure cost. Each container deployed will be approximately US$57.25 per month on the default configuration provided by Devant. Additional resources will be charged based on the type of resource required.
- **Example 2**: Creating, deploying, and managing a microservice; the same approach as example 1.

### Q: What are the integration limitations?

- **Developer plan**: Allows up to a maximum of five free integrations and unlimited paid integrations.
- **PAYG plan**: Allows unlimited paid integrations.
- **Enterprise plan**: Allows unlimited paid integrations.

### Q: How do I read the bill?
Your bill will detail the number of integrations used, infrastructure consumed, support plans used, and any additional services you may have purchased. If you are unsure about any charges on your bill, reach out to devant-help@wso2.com for clarification.

### Q: Is support included in the Devant Enterprise plan?
The Devant Enterprise plan does not automatically include support; however, you can purchase support plans in addition to the Enterprise plan at any time. Find out more at https://wso2.com/saas-support-plans/.

### Q: I am an Enterprise subscription customer who wants to use the Devant private data plane. What costs will I incur in addition to the subscription and support plan?
You can start by using a basic plan or contact us for an Enterprise support plan.

### Q: I want to upgrade from PAYG to an Enterprise subscription. Will there be an outage during the upgrade?
No, there are no outages when upgrading a plan.
