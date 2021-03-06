﻿---
title: 'Change the offline address book generation schedule: Exchange 2013 Help'
TOCTitle: Change the offline address book generation schedule
ms:assetid: d2b4d527-311e-442d-9f1f-54fac8371b80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Bb124719(v=EXCHG.150)
ms:contentKeyID: 49289420
ms.date: 12/10/2017
mtps_version: v=EXCHG.150
f1_keywords:
- Microsoft.Exchange.Management.SnapIn.Esm.OrganizationConfiguration.Mailbox.OfflineAddressBookGeneralPage
---

# Change the offline address book generation schedule

 

_**Applies to:** Exchange Server 2013_


An offline address book (OAB) is a copy of an address book that's been downloaded so that an Outlook user can access the information it contains while disconnected from the server. You can configure how often the OAB is generated by using the *OABGeneratorWorkCycle* and *OABGeneratorWorkCycleCheckpoint* parameters on the Set-MailboxServer cmdlet.

For additional management tasks related to OABs, see [Offline address book procedures](offline-address-book-procedures-exchange-2013-help.md).

## What do you need to know before you begin?

  - Estimated time to complete each procedure: 5 minutes.

  - You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Offline address books" entry in the [Email address and address book permissions](email-address-and-address-book-permissions-exchange-2013-help.md) topic.

  - You can’t use the Exchange Administration center (EAC) to perform this procedure. You must use the Shell.

  - For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center](keyboard-shortcuts-in-the-exchange-admin-center-exchange-online-protection-help.md).


> [!TIP]
> Having problems? Ask for help in the Exchange forums. Visit the forums at <A href="https://go.microsoft.com/fwlink/p/?linkid=60612">Exchange Server</A>, <A href="https://go.microsoft.com/fwlink/p/?linkid=267542">Exchange Online</A>, or <A href="https://go.microsoft.com/fwlink/p/?linkid=285351">Exchange Online Protection</A>.



## Use the Shell to configure OAB properties

In this example, the offline address book is generated every six hours each day on the Mailbox server, MBXServer01.

    Set-MailboxServer -Identity MBXServer01 -OABGeneratorWorkCycle 01.00:00:00 -OABGeneratorWorkCycleCheckpoint 06:00:00 

For detailed syntax and parameter information, see [Set-OfflineAddressBook](https://technet.microsoft.com/en-us/library/aa996330\(v=exchg.150\)).

