---
title: "System.Runtime.InteropServices.DllImportAttribute kann nicht auf eine Methode angewendet werden, die generisch oder in einem generischen Typ geschachtelt ist"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc31526"
  - "bc31526"
helpviewer_keywords: 
  - "BC31526"
ms.assetid: 6f153808-1945-4c99-85ae-8bd3b35ee5a2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# System.Runtime.InteropServices.DllImportAttribute kann nicht auf eine Methode angewendet werden, die generisch oder in einem generischen Typ geschachtelt ist
Eine Prozedur ist mit dem <xref:System.Runtime.InteropServices.DllImportAttribute> deklariert, aber entweder ist die Prozedur generisch oder in einer generischen Klasse oder Struktur enthalten.  
  
 Die Common Language Runtime \(CLR\) erkennt, dass dieses Attribut und seine <xref:System.Runtime.InteropServices._Assembly.EntryPoint*>\-Eigenschaft eine Ersetzungsprozedur angeben, die in einer nicht verwalteten DLL \(Dynamic Link Library\) außerhalb von .NET Framework definiert ist. Wenn Code die Prozedur aufruft, auf die <xref:System.Runtime.InteropServices.DllImportAttribute> angewendet wird, ruft die Common Language Runtime stattdessen die angegebene nicht verwaltete Prozedur auf.  
  
 Da nicht verwaltete Plattformen außerhalb von .NET Framework generische Typen nicht erkennen, können Sie nicht mit diesen Plattformen unter Verwendung von generischen Typen interoperieren.  
  
 **Fehler\-ID:** BC31526  
  
### So beheben Sie diesen Fehler  
  
-   Wenn weder die Prozedur noch ihr Container generisch sein muss, entfernen Sie die `Of`\-Klauseln, sodass sie nicht generisch sind.  
  
-   Wenn die Prozedur oder ihr Container generisch sein muss, entfernen Sie das <xref:System.Runtime.InteropServices.DllImportAttribute> aus der Deklaration dieser Prozedur.  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)