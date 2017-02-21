---
title: "Vorrang in R&#252;ckschlussregeln | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rückschlussregeln in NMAKE"
  - "Rangfolge, Rückschlussregel"
  - "Regeln, Rückschluss"
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Vorrang in R&#252;ckschlussregeln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn eine Rückschlussregel mehrfach definiert ist, wird von NMAKE die Definition mit der höchsten Priorität eingesetzt.  Die folgende Liste zeigt die Rangfolge von oben nach unten an:  
  
1.  Eine Rückschlussregel, die in einem Makefile definiert wurde. Später erfolgende Definitionen werden vorrangig behandelt.  
  
2.  Eine Rückschlussregel, die in der Datei Tools.ini definiert wurde. Später erfolgende Definitionen werden vorrangig behandelt.  
  
3.  Eine vordefinierte Rückschlussregel.  
  
## Siehe auch  
 [Rückschlussregeln](../build/inference-rules.md)