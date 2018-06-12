﻿---
title: 'Configure the secondary way for Outlook Voice Access users to search: Exchange 2013 Help'
TOCTitle: Configure the secondary way for Outlook Voice Access users to search
ms:assetid: 5cd4e0a0-d023-45a1-aa3c-b8dea6ec6d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Aa998311(v=EXCHG.150)
ms:contentKeyID: 49315425
ms.date: 12/10/2017
mtps_version: v=EXCHG.150
---

# Configure the secondary way for Outlook Voice Access users to search

 

_**Applies to:** Exchange Online, Exchange Server 2013, Exchange Server 2016_


When you create a dial plan, you can configure the primary and secondary *dial by name methods* or ways that callers can search for names. Callers use these dial by name methods to look up names to locate and contact a user when they call in to an Outlook Voice Access number or when they call in to a UM auto attendant that's associated with the dial plan. Callers can use touchtone inputs to locate a UM-enabled user.


> [!NOTE]
> If <STRONG>None</STRONG> is selected as the secondary way for callers to search for names, only the primary way of searching for names will be available to callers who want to locate users. If you configure both the primary and secondary ways that callers can search for names, callers will be prompted for both ways.



For additional management tasks related to UM dial plans, see [UM dial plan procedures](um-dial-plan-procedures-exchange-2013-help.md).

## What do you need to know before you begin?

  - Estimated time to complete: Less than 1 minute.

  - You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "UM dial plans" entry in the [Unified Messaging permissions](unified-messaging-permissions-exchange-2013-help.md) topic.

  - Before you perform these procedures, confirm that a UM dial plan has been created. For detailed steps, see [Create a UM dial plan](create-a-um-dial-plan-exchange-2013-help.md).

  - For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center](keyboard-shortcuts-in-the-exchange-admin-center-exchange-online-protection-help.md).


> [!TIP]
> Having problems? Ask for help in the Exchange forums. Visit the forums at <A href="https://go.microsoft.com/fwlink/p/?linkid=60612">Exchange Server</A>, <A href="https://go.microsoft.com/fwlink/p/?linkid=267542">Exchange Online</A>, or <A href="https://go.microsoft.com/fwlink/p/?linkid=285351">Exchange Online Protection</A>..



## What do you want to do?

## Use the EAC to change the secondary dial by name method

1.  In the EAC, navigate to **Unified Messaging** \> **UM dial plans**.

2.  In the list view, select the UM dial plan you want to change, and then click **Edit** ![Edit icon](images/JJ218640.6f53ccb2-1f13-4c02-bea0-30690e6ea71d(EXCHG.150).gif "Edit icon").

3.  On the **UM Dial Plan** page, click **Configure**.

4.  In **Settings**, under **Secondary way to search for names**, use the drop-down list to select the option you want:
    
      - **Last first** (default)
    
      - **First last**
    
      - **SMTP address**
    
      - **None**

5.  Click **Save**.

## Use the Shell to change the secondary dial by name method

This example sets the secondary dial by name method to `FirstLast`. This enables callers who call the Outlook Voice Access number or a UM auto attendant associated with the dial plan to search for a UM-enabled user by their first and then last name.

    Set-UMDialPlan -Identity MyUMDialPlan -DialByNameSecondary FirstLast

This example sets the secondary dial by name method to `LastFirst`. This enables callers who call the Outlook Voice Access number or a UM auto attendant associated with the dial plan to search for a UM-enabled user by their last and then first name.

    Set-UMDialPlan -Identity MyUMDialPlan -DialByNameSecondary LastFirst 

This example sets the secondary dial by name method to `SMTP address`. This enables callers who call the Outlook Voice Access number or a UM auto attendant associated with the dial plan to search for a UM-enabled user by their SMTP address.

    Set-UMDialPlan -Identity MyUMDialPlan -DialByNameSecondary SMTPAddress 

This example sets the secondary dial by name method to `None` and the primary dial by name method to `SMTP address`. This enables callers who call the Outlook Voice Access number or a UM auto attendant associated with the dial plan to search for a UM-enabled user by their SMTP address only.

    Set-UMDialPlan -Identity MyUMDialPlan -DialByNamePrimary SMTPAddress -DialByNameSecondary None
