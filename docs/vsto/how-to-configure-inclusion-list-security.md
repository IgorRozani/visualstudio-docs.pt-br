---
title: 'How to: Configure Inclusion List Security | Microsoft Docs'
ms.custom: 
ms.date: 02/02/2017
ms.prod: visual-studio-dev14
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio
- inclusion lists [Office development in Visual Studio]
ms.assetid: 0609d8f0-4630-4e17-aeb3-14f3134165cf
caps.latest.revision: 26
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: ddda79fad6b114c7b91a4b05df82433fe59a0f3d
ms.contentlocale: pt-br
ms.lasthandoff: 08/28/2017

---
# <a name="how-to-configure-inclusion-list-security"></a>How to: Configure Inclusion List Security
  If you have Administrator permissions, you can configure the [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] trust prompt to control whether end users are given the option of installing Office solutions by saving a trust decision to the inclusion list. For information about inclusion lists, see [Trusting Office Solutions by Using Inclusion Lists](../vsto/trusting-office-solutions-by-using-inclusion-lists.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 For solutions that are in each of five zones, you can set the following options:  
  
-   Enable the [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] Trust Prompt Key and the inclusion list. You can allow end users to grant trust to Office solutions that are signed with any certificate.  
  
-   Restrict the [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] Trust Prompt Key and the inclusion list. You can allow end users to install Office solutions that are signed with a certificate that identifies the publisher, but that is not already trusted.  
  
-   Disable the [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] Trust Prompt Key and the inclusion list. You can prevent end users from installing any Office solution that is not signed with an explicitly trusted certificate.  
  
## <a name="enabling-the-inclusion-list"></a>Enabling the Inclusion List  
 Enable the inclusion list for a zone when you want end users to be presented with the option of installing and running any Office solution that comes from that zone.  
  
#### <a name="to-enable-the-inclusion-list-by-using-the-registry-editor"></a>To enable the inclusion list by using the registry editor  
  
1.  Open the registry editor:  
  
    1.  Click **Start**, and then click **Run**.  
  
    2.  In the **Open** box, type **regedt32.exe**, and then click **OK**.  
  
2.  Find the following registry key:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\.NETFramework\Security\TrustManager\PromptingLevel  
  
     If the key does not exist, create it.  
  
3.  Add the following subkeys as **String Value**, if they do not already exist, with the associated values.  
  
    |String Value subkey|Value|  
    |-------------------------|-----------|  
    |**Internet**|**AuthenticodeRequired**|  
    |**UntrustedSites**|**Disabled**|  
    |**MyComputer**|**Enabled**|  
    |**LocalIntranet**|**Enabled**|  
    |**TrustedSites**|**Enabled**|  
  
     By default, **Internet** has the value **AuthenticodeRequired** and **UntrustedSites** has the value **Disabled**.  
  
#### <a name="to-enable-the-inclusion-list-programmatically"></a>To enable the inclusion list programmatically  
  
1.  Create a Visual Basic or Visual C# console application.  
  
2.  Open the Program.vb or Program.cs file for editing and add the following code.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Enabled")  
    key.SetValue("LocalIntranet", "Enabled")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "Enabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Enabled");  
    key.SetValue("LocalIntranet", "Enabled");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "Enabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Build and run the application.  
  
## <a name="restricting-the-inclusion-list"></a>Restricting the Inclusion List  
 Restrict the inclusion list so that solutions must be signed with Authenticode certificates that have known identity before users are prompted for a trust decision.  
  
#### <a name="to-restrict-the-inclusion-list"></a>To restrict the inclusion list  
  
1.  Open the registry editor:  
  
    1.  Click **Start**, and then click **Run**.  
  
    2.  In the **Open** box, type **regedt32.exe**, and then click **OK**.  
  
2.  Find the following registry key:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\.NETFramework\Security\TrustManager\PromptingLevel  
  
     If the key does not exist, create it.  
  
3.  Add the following subkeys as **String Value**, if they do not already exist, with the associated values.  
  
    |String Value subkey|Value|  
    |-------------------------|-----------|  
    |**UntrustedSites**|**Disabled**|  
    |**Internet**|**AuthenticodeRequired**|  
    |**MyComputer**|**AuthenticodeRequired**|  
    |**LocalIntranet**|**AuthenticodeRequired**|  
    |**TrustedSites**|**AuthenticodeRequired**|  
  
     By default, **Internet** has the value **AuthenticodeRequired** and **UntrustedSites** has the value **Disabled**.  
  
#### <a name="to-restrict-the-inclusion-list-programmatically"></a>To restrict the inclusion list programmatically  
  
1.  Create a Visual Basic or Visual C# console application.  
  
2.  Open the Program.vb or Program.cs file for editing and add the following code.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "AuthenticodeRequired")  
    key.SetValue("LocalIntranet", "AuthenticodeRequired")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "AuthenticodeRequired")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "AuthenticodeRequired");  
    key.SetValue("LocalIntranet", "AuthenticodeRequired");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "AuthenticodeRequired");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Build and run the application.  
  
## <a name="disabling-the-inclusion-list"></a>Disabling the Inclusion List  
 You can disable the inclusion list so that end users can only install solutions that are signed with a trusted and known certificate.  
  
#### <a name="to-disable-the-inclusion-list"></a>To disable the inclusion list  
  
1.  Open the registry editor:  
  
    1.  Click **Start**, and then click **Run**.  
  
    2.  In the **Open** box, type **regedt32.exe**, and then click **OK**.  
  
2.  Create the following registry key if this does not already exist:  
  
     **\HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\.NETFramework\Security\TrustManager\PromptingLevel**  
  
3.  Add the following subkeys as **String Value**, if they do not already exist, with the associated values.  
  
    |String Value subkey|Value|  
    |-------------------------|-----------|  
    |**UntrustedSites**|**Disabled**|  
    |**Internet**|**Disabled**|  
    |**MyComputer**|**Disabled**|  
    |**LocalIntranet**|**Disabled**|  
    |**TrustedSites**|**Disabled**|  
  
#### <a name="to-disable-the-inclusion-list-programmatically"></a>To disable the inclusion list programmatically  
  
1.  Create a Visual Basic or Visual C# console application.  
  
2.  Open the Program.vb or Program.cs file for editing and add the following code.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Disabled")  
    key.SetValue("LocalIntranet", "Disabled")  
    key.SetValue("Internet", "Disabled")  
    key.SetValue("TrustedSites", "Disabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Disabled");  
    key.SetValue("LocalIntranet", "Disabled");  
    key.SetValue("Internet", "Disabled");  
    key.SetValue("TrustedSites", "Disabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
  
    ```  
  
3.  Build and run the application.  
  
## <a name="see-also"></a>See Also  
 [Trusting Office Solutions by Using Inclusion Lists](../vsto/trusting-office-solutions-by-using-inclusion-lists.md)   
 [Securing Office Solutions](../vsto/securing-office-solutions.md)  
  
  