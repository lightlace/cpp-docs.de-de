---
title: "Compilerfehler CS0167"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0167"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0167"
ms.assetid: e6901b40-11a0-422c-9ea3-3b25c0ad7791
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0167
Für Delegat 'Delegat' fehlt die Invoke\-Methode.  
  
 Sie haben ein verwaltetes Programm \(das die Common Language Runtime von .NET Framework verwendet\) importiert und verwendet, das mit einem anderen Compiler erstellt wurde. Dieser Compiler hat einen falsch formatierten [Delegaten](../Topic/delegate%20\(C%23%20Reference\).md) zugelassen. Aus diesem Grund war die `Invoke`\-Methode nicht verfügbar. Weitere Informationen finden Sie unter [Delegaten](../Topic/Delegates%20\(C%23%20Programming%20Guide\).md).