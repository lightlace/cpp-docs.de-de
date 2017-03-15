---
title: "RECORD (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RECORD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RECORD directive"
ms.assetid: c83db394-0fe3-468f-813f-13302cdc862d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# RECORD (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Deklariert einen Datensatztyp, die aus den angegebenen Feldern besteht.  *Feldnamen* benennt das Feld *Breite* gibt die Anzahl der Bits und *Ausdruck* gibt ihren Startwert.  
  
## Syntax  
  
```  
  
   recordname RECORD fieldname:width [[= expression]]   
[[, fieldname:width [[= expression]]]]...  
```  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)