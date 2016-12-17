---
title: "&#39;&lt;Member&gt;&#39; verursacht einen Konflikt mit dem gleichnamigen reservierten Member, der in allen Enumerationen explizit deklariert wurde."
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
  - "bc31420"
  - "vbc31420"
helpviewer_keywords: 
  - "BC31420"
ms.assetid: f2ea5a8b-f63c-4c93-bfac-418ae5a150a5
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;Member&gt;&#39; verursacht einen Konflikt mit dem gleichnamigen reservierten Member, der in allen Enumerationen explizit deklariert wurde.
Der Name eines Typmembers steht in Konflikt mit dem Namen eines implizit in allen Enumerationen deklarierten Members.  
  
 Der [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]\-Compiler erstellt implizite Member, die bestimmten von Ihnen deklarierten Programmierelementen entsprechen. Enumerationen deklarieren den `value__member`\-Member implizit.  
  
 **Fehler\-ID:** BC31420  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie den Namen des Members.  
  
## Siehe auch  
 [NotInBuild: Deklarationsanweisungen in Visual Basic](assetId:///81f3c398-f45c-4d95-80bf-aa39d1a0fb30)   
 [Enumerations Overview](../Topic/Enumerations%20Overview%20\(Visual%20Basic\).md)   
 [Declared Element Names](../Topic/Declared%20Element%20Names%20\(Visual%20Basic\).md)