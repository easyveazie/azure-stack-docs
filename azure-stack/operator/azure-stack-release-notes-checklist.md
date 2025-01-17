---
title: Azure Stack update activity checklist | Microsoft Docs
description:  Checklist to prepare your system for the latest Azure Stack update.
services: azure-stack
documentationcenter: ''
author: sethmanheim
manager: femila
editor: ''

ms.assetid:  
ms.service: azure-stack
ms.workload: na
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 08/22/2019
ms.author: sethm
ms.reviewer: hectorl
ms.lastreviewed: 08/22/2019

---

# Azure Stack update activity checklist

*Applies to: Azure Stack integrated systems*

Review this checklist in order to prepare for an Azure Stack update. This article contains a checklist of update-related activities for Azure Stack operators.

## Prepare for Azure Stack update

| Activity | Details |
| --- | --- |
| Review known issues |[List of known issues](https://docs.microsoft.com/azure-stack/operator/azure-stack-release-notes-known-issues-1906). |
| Review security updates | [List of security updates](https://docs.microsoft.com/azure-stack/operator/azure-stack-release-notes-security-updates-1906). |
| Apply latest OEM package | Contact your OEM to ensure your system meets the minimum OEM Package requirements for the Azure Stack version your system is being updated to. |
| Run Test-AzureStack | Run `Test-AzureStack -Group UpdateReadiness` to identify operational issues. |
| Resolve issues | Resolve any operational issues identified by `Test-AzureStack`. |
| Apply latest hotfixes | Apply the latest hotfixes that apply to the currently installed release. |
| Run capacity planner tool | Make sure to use the latest version of the Azure Stack Capacity Planner tool to perform your workload planning and sizing. The latest version contains bug fixes and provides new features that are released with each Azure Stack update. |
| Update available | In connected scenarios only, Azure Stack deployments periodically check a secured endpoint and automatically notify you if an update is available for your cloud. Disconnected customers can download and import new packages using the [process described here](https://docs.microsoft.com/azure-stack/operator/azure-stack-apply-updates). |


## During Azure Stack update

| Activity | Details |
|--------------------|------------------------------------------------------------------------------------------------------|
| Manage the update |[Manage updates in Azure Stack using the operator portal](https://docs.microsoft.com/azure-stack/operator/azure-stack-updates). |
|  |  |
| Monitor the update | If the operator portal is unavailable, [monitor updates in Azure Stack using the privileged endpoint](https://docs.microsoft.com/azure-stack/operator/azure-stack-monitor-update). |
|  |  |
| Resume updates | After remediating a failed update, [resume updates in Azure Stack using the privileged endpoint](https://docs.microsoft.com/azure-stack/operator/azure-stack-monitor-update). |

> [!Important]  
> Do not run **Test-AzureStack** during an update, as this will cause the update to stall.

## After Azure Stack update

| Activity | Details |
|--------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Apply latest hotfixes | Apply the latest hotfixes applicable to updated version. |
| Retrieve encryption keys | Retrieve the data at rest encryption keys and securely store them outside of your Azure Stack deployment. Follow the [instructions on how to retrieve the keys](https://docs.microsoft.com/azure-stack/operator/azure-stack-security-bitlocker). |
|  |  |
| Re-enable multi-tenancy | In case of a multi-tenanted Azure Stack, [make sure you configure all guest directory tenants](https://docs.microsoft.com/azure-stack/operator/azure-stack-enable-multitenancy#configure-guest-directory) after a successful update. |

## Next steps

-   [Review list of known issues](https://docs.microsoft.com/azure-stack/operator/azure-stack-release-notes-known-issues-1907)  
-   [Review list of security updates](https://docs.microsoft.com/azure-stack/operator/azure-stack-release-notes-security-updates-1907)