---
# required metadata

title: Working with Azure ATP Reports | Microsoft Docs
description: Describes how you can generate reports in Azure ATP to monitor your network.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/27/2018
ms.topic: conceptual
ms.prod:
ms.service: azure-advanced-threat-protection
ms.technology:
ms.assetid: 2c2d6b1a-fc8c-4ff7-b07d-64ce6159f84d


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: itargoet
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

*Applies to: Azure Advanced Threat Protection*


# Azure ATP Reports

The Azure ATP reports section in the workspace portal enables you to generate reports that provide you with system status information, both system health and a report of the suspicious activities detected in your environment.


To access the reports page, click the report icon in the menu bar: ![report icon](./media/atp-report-icon.png).
The reports that are available are: 

- **Summary report**: The Summary report presents a dashboard of the status in the system. You can view three tabs - one for a **Summary** of what was detected on your network, **Open suspicious activities** that lists the suspicious activities you should take care of, and **Open health issues** that lists Azure ATP health issues you should take care of. The suspicious activities listed are broken down by type, as are the health issues. 

- **Modification of sensitive groups**: This report lists every time a modification is made to sensitive groups (such as admins, or manually tagged accounts or groups). If you're using Azure ATP standalone sensors, to receive a full report about your sensitive groups, it is necessary to make sure that [events are forwarded from your domain controllers to the standalone sensors](configure-event-forwarding.md). 

- **Passwords exposed in cleartext**: Some services use the LDAP non-secure protocol to send account credentials in plain text. This can even happen for sensitive accounts. Attackers monitoring network traffic can catch and then reuse these credentials for malicious purposes. This report lists all source computer and account passwords that Azure ATP detected as being sent in clear text. 

- **Lateral movement paths to sensitive accounts**: This report lists the sensitive accounts that are exposed via lateral movement paths. For more information, see [Lateral movement paths](use-case-lateral-movement-path.md). This report collects paths that were created in the last 60 days, as opposed to the information displayed in the workspace portal, which represents only two days.

There are two ways to generate a report: either on demand or by scheduling a report to be sent to your email periodically.

To generate a report on demand:

1. In the Azure ATP workspace portal menu bar, click the report icon in the menu bar: ![report icon](./media/atp-report-icon.png).

2. Under either your selected report type, set the **From** and **To** dates and click **Download**. 
 ![reports](./media/reports.png)

To set a scheduled report:
 
1. In the **Reports** page, click **Set scheduled reports**, or in the Azure ATP workspace portal configuration page, under Notifications and Reports, click **Scheduled reports**.

   ![Schedule reports](./media/atp-sched-reports.png)
 
 > [!NOTE]
 > The daily reports are designed to be sent shortly after midnight, UTC.

2. Click **Schedule** next to your selected report type, to set the frequency and email address for delivery of the reports, and click the plus sign next to the email addresses to add them, and click **Save**.

   ![Schedule report frequency and email](./media/sched-report1.png)


## See Also
- [Azure ATP prerequisites](atp-prerequisites.md)
- [Azure ATP capacity planning](atp-capacity-planning.md)
- [Configure event collection](configure-event-collection.md)
- [Configuring Windows event forwarding](configure-event-forwarding.md#configuring-windows-event-forwarding)
- [Check out the ATP forum!](https://aka.ms/azureatpcommunity)