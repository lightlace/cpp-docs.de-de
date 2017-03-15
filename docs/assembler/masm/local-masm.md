---
title: "LOCAL (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Local"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LOCAL directive"
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# LOCAL (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In den ersten \- Direktive innerhalb eines Makros definiert **LOKAL** Bezeichnungen, die auf jede Instanz des Makros eindeutig sind.  
  
## Syntax  
  
```  
  
      LOCAL localname [[, localname]]...  
LOCAL label [[ [count ] ]] [[:type]] [[, label [[ [count] ]] [[type]]]]...  
```  
  
## Hinweise  
 In den zweiten \- Direktive in der Prozedurdefinition \(**PROC**\), erstellt **LOKAL** Stapel\-basierte Variablen, die für die Dauer der Prozedur vorhanden sind.  Die *Bezeichnung* ist möglicherweise eine einfache Variable oder ein Array mit der *Anzahl* der Elemente enthalten.  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)