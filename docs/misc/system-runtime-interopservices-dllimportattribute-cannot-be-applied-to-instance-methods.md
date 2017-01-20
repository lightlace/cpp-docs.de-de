---
title: "System.Runtime.InteropServices.DllImportAttribute kann nicht auf Instanzmethoden angewendet werden"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc31529"
  - "bc31529"
helpviewer_keywords: 
  - "BC31529"
ms.assetid: c8bde5d7-c6bf-4d21-bb1a-e8627d65ad29
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "shoag"
manager: "wpickett"
---
# System.Runtime.InteropServices.DllImportAttribute kann nicht auf Instanzmethoden angewendet werden
Eine nicht freigegebene Prozedur ist mit dem <xref:System.Runtime.InteropServices.DllImportAttribute> deklariert.  
  
 Die Common Language Runtime \(CLR\) erkennt, dass dieses Attribut und seine <xref:System.Runtime.InteropServices._Assembly.EntryPoint*>\-Eigenschaft eine Ersetzungsprozedur angeben, die in einer nicht verwalteten DLL \(Dynamic Link Library\) außerhalb von .NET Framework definiert ist. Wenn Code die Prozedur aufruft, auf die <xref:System.Runtime.InteropServices.DllImportAttribute> angewendet wird, ruft die Common Language Runtime stattdessen die angegebene nicht verwaltete Prozedur auf.  
  
 Da nicht verwaltete Plattformen außerhalb von .NET Framework nicht freigegebene Prozeduren nicht auf dieselbe Weise wie .NET Framework unterstützen, ist die Interoperation mit diesen Plattformen unter Verwendung nicht freigegebener Prozeduren nicht möglich.  
  
 **Fehler\-ID:** BC31529  
  
### So beheben Sie diesen Fehler  
  
-   Wenn die Prozedur nicht einzeln auf jede Instanz ihrer Klasse oder Struktur angewendet werden muss, deklarieren Sie sie als `Shared`.  
  
-   Wenn die Prozedur nicht `Shared` sein darf, entfernen Sie das <xref:System.Runtime.InteropServices.DllImportAttribute> aus der Deklaration dieser Prozedur.  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Shared](../Topic/Shared%20\(Visual%20Basic\).md)