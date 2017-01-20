---
title: "MSBuild Error MSB3256"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "MSB3256"
ms.assetid: 809ccd0a-78cd-4bf5-83a8-2fb51815ea27
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3256
**MSB3256: Aus den redist\-Listen wurden keine Assemblys gelesen.  Es konnte keine Ausschlussliste für die TargetFramework\-Teilmenge generiert werden.**  
  
 Es wurde keine Liste verteilbarer Elemente \(REDIST\-Liste\) gefunden.  
  
 Zum Generieren einer Liste der Assemblys, die aus der .NET Framework\-Teilmenge auszuschließen sind, werden zwei Dateien benötigt: eine "REDIST\-Liste" mit dem Namen "FrameworkList.xml", die die Namen der verteilbaren Elemente in .NET Framework enthält, und eine "Teilmengenliste" mit dem Namen "client.xml", die die Namen der Elemente in .NET Framework enthält.  Da die Teilmengendefinition beide Listen erfordert, kann die .NET Framework\-Teilmenge nicht aufgerufen werden, wenn die REDIST\-Liste fehlt.  
  
 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] ist eine Teilmenge der vollständigen [!INCLUDE[net_v35_short](../misc/includes/net_v35_short_md.md)]\-Laufzeitbibliothek.  Weitere Informationen zum [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] finden Sie unter [.NET Framework Client Profile](../Topic/.NET%20Framework%20Client%20Profile.md).  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie entweder eine gültige REDIST\-Liste mit dem Namen \<legacyBold\>FrameworkList.xml\<\/legacyBold\> zur Verfügung, oder geben Sie die vollständige verteilbare [!INCLUDE[net_v35_short](../misc/includes/net_v35_short_md.md)]\-Bibliothek als Ziel an.  Weitere Informationen darüber, wie Sie die vollständige [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] als Ziel angeben, finden Sie unter [Gewusst wie: .NET Framework\-Version als Ziel](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
## Siehe auch  
 [Target Framework and Target Platform](../Topic/MSBuild%20Target%20Framework%20and%20Target%20Platform.md)   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [Additional Resources](../Topic/Additional%20MSBuild%20Resources.md)