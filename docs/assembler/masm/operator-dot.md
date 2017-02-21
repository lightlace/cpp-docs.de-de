---
title: "operator . | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "operator ."
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dot operator (.)"
  - "operator ."
  - ". operator"
ms.assetid: 468ea0c8-5b08-47be-991b-38abacb77611
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# operator .
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der erste Operator gibt *Ausdruck* sowie den Offset *des Felds* innerhalb der Struktur oder Union zurück.  Der zweite Operator gibt einen Wert zurück, der an der Position *zu registrierende* plus den Offset *des Felds* innerhalb der Struktur oder Union dargestellt wird.  
  
## Syntax  
  
```  
  
      expression  
      . field [[. field]]...  
[register]. field [[. field]]...  
```  
  
## Siehe auch  
 [Operators Reference](../../assembler/masm/operators-reference.md)