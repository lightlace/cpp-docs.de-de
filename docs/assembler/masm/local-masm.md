---
title: "LOCAL (MASM)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "Local"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LOCAL directive"
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
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