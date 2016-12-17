---
title: "&#39;Option Strict On&#39; l&#228;sst das Einschr&#228;nken impliziter Typkonvertierungen zwischen der Erweiterungsmethode &#39;&lt;erweiterungsmethodenname&gt;&#39;, die in &#39;&lt;modulname&gt;&#39; definiert ist, und dem Delegaten &#39;&lt;delegatname&gt;&#39; nicht zu."
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
  - "bc36709"
  - "vbc36709"
helpviewer_keywords: 
  - "BC36709"
ms.assetid: 95d8c833-3525-411b-98e8-b7d3f61f75c9
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Option Strict On&#39; l&#228;sst das Einschr&#228;nken impliziter Typkonvertierungen zwischen der Erweiterungsmethode &#39;&lt;erweiterungsmethodenname&gt;&#39;, die in &#39;&lt;modulname&gt;&#39; definiert ist, und dem Delegaten &#39;&lt;delegatname&gt;&#39; nicht zu.
Mit aktiviertem `Option Strict` können Sie keine einschränkende Konvertierung vom Datentyp eines Parameters in einem Delegaten zum entsprechenden Parameter einer Erweiterungsmethode, der einer Variablen dieses Delegattyps zugewiesen ist, vornehmen. Der Datentyp des Delegatparameters muss zum Datentyp der Erweiterungsmethode erweitert werden.  
  
 **Fehler\-ID:** BC36709  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie den Datentyp des Parameters im Delegaten oder der Erweiterungsmethode so, dass sich die erforderliche erweiternde Beziehung ergibt.  
  
## Siehe auch  
 [Erweiterungsmethoden](../Topic/Extension%20Methods%20\(Visual%20Basic\).md)   
 [Relaxed Delegate Conversion](../Topic/Relaxed%20Delegate%20Conversion%20\(Visual%20Basic\).md)   
 [Delegates](../Topic/Delegates%20\(Visual%20Basic\).md)   
 [Widening and Narrowing Conversions](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md)   
 [NICHT IM BUILD: Delegaten und der AddressOf\-Operator](assetId:///7b2ed932-8598-4355-b2f7-5cedb23ee86f)