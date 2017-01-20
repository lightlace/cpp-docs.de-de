---
title: "&#39;System.Runtime.InteropServices.DllImportAttribute&#39; kann nicht auf Schnittstellenmethoden angewendet werden."
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
  - "bc31530"
  - "vbc31530"
helpviewer_keywords: 
  - "BC31530"
ms.assetid: e63f1f7d-b7df-4637-a0f4-2783479ca1af
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;System.Runtime.InteropServices.DllImportAttribute&#39; kann nicht auf Schnittstellenmethoden angewendet werden.
Eine Prozedur ist in einer Schnittstelle definiert, aber die Definition der Prozedur wendet das <xref:System.Runtime.InteropServices.DllImportAttribute> an.  
  
 Die Common Language Runtime \(CLR\) erkennt, dass dieses Attribut und seine <xref:System.Runtime.InteropServices._Assembly.EntryPoint*>\-Eigenschaft eine Ersetzungsprozedur angeben, die in einer nicht verwalteten DLL \(Dynamic Link Library\) außerhalb von .NET Framework definiert ist. Wenn die Prozedur im Code aufgerufen wird, auf die <xref:System.Runtime.InteropServices.DllImportAttribute> angewendet wird, ruft die Common Language Runtime stattdessen die angegebene nicht verwaltete Prozedur auf.  
  
 Da die Definition einer Prozedur innerhalb einer Schnittstelle keine Implementierung umfasst, kann sie mit nicht verwalteten Plattformen außerhalb von .NET Framework nicht zusammenarbeiten.  
  
 **Fehler\-ID:** BC31530  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das <xref:System.Runtime.InteropServices.DllImportAttribute> aus der Definition dieser Prozedur.  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Interface Statement](../Topic/Interface%20Statement%20\(Visual%20Basic\).md)