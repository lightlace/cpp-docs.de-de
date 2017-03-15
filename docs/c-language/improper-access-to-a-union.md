---
title: "Unsachgem&#228;&#223;er Zugriff auf eine Union | Microsoft Docs"
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
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Unsachgem&#228;&#223;er Zugriff auf eine Union
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.3.2.3** Auf ein Member eines union\-Objekts wird mithilfe eines Members eines anderen Typs zugegriffen  
  
 Wenn eine Union von zwei Typen deklariert wird und ein Wert gespeichert ist, aber mit dem anderen Typ auf die Union zugegriffen wird, sind die Ergebnisse unzuverlässig.  
  
 Beispielsweise wird eine Union von **float** und `int` deklariert.  Ein **float**\-Wert wird gespeichert, aber später greift das Programm auf den Wert als `int` zu.  In einer solchen Situation ist der Wert der internen Speicherung von **float**\-Werten abhängig.  Der Ganzzahlwert wäre nicht zuverlässig.  
  
## Siehe auch  
 [Strukturen, Unions, Enumerationen und Bitfelder](../c-language/structures-unions-enumerations-and-bit-fields.md)