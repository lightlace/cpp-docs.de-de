---
title: "Zu viele Clients f&#252;r die DLL-Anwendung"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbrID47"
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Zu viele Clients f&#252;r die DLL-Anwendung
Die Dynamic Link Library \(DLL\) für [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] kann nur einer begrenzten Anzahl von Hostanwendungen Zugriff gewähren. Ihre Anwendung und andere Clientanwendungen, die [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]\- Hosts sind \(von denen auf einige möglicherweise von Ihrer Anwendung zugegriffen wird\), versuchen gleichzeitig, auf die [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]\-DLL zuzugreifen.  
  
### So beheben Sie diesen Fehler  
  
-   Reduzieren Sie die Anzahl der geöffneten Anwendungen, die auf [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] zugreifen.  
  
## Siehe auch  
 [Error Types](../Topic/Error%20Types%20\(Visual%20Basic\).md)