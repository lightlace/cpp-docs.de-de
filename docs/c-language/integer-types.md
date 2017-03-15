---
title: "Ganzzahltypen | Microsoft Docs"
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
  - "Ganzzahlkonstanten"
  - "integer-Datentyp, Ganzzahltypen in C++"
  - "Ganzzahltypen"
  - "Ganze Zahlen, Typen"
ms.assetid: c8926a5e-0e98-4e37-9b05-ce97961379bd
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Ganzzahltypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Allen Integerkonstanten wird ein Typ anhand ihres Werts und der Ausdrucksmethode zugewiesen.  Sie können eine Integerkonstante auf den Typ **long** erzwingen, indem Sie den Buchstaben **l** oder **L** am Ende der Konstante anfügen. Sie können die Integerkonstante auf den Typ `unsigned` erzwingen, indem Sie **u** oder **U** an den Wert anfügen.  Der Kleinbuchstabe **l** kann mit der Ziffer 1 verwechselt werden und sollte daher nicht angefügt werden.  Einige Formen der **long**\-Integerkonstanten folgen:  
  
```  
/* Long decimal constants */  
10L  
79L  
  
/* Long octal constants */  
012L  
0115L  
  
/* Long hexadecimal constants */  
0xaL or 0xAL  
0X4fL or 0x4FL  
  
/* Unsigned long decimal constant */  
776745UL  
778866LU  
```  
  
 Der Typ, den Sie einer Konstanten zuweisen, hängt von dem Wert ab, den die Konstante darstellt.  Der Wert einer Konstante muss im Bereich der darstellbaren Werte für ihren Typ liegen.  Ein Konstantentyp bestimmt, welche Konvertierungen ausgeführt werden, wenn die Konstante in einem Ausdruck verwendet oder das Minuszeichen \(**–**\) angewendet wird.  In dieser Liste werden die Konvertierungsregeln für Integerkonstanten zusammengefasst.  
  
-   Eine Dezimalkonstante ohne Suffix ist vom Typ `int`, **long int** oder **unsigned long int**.  Der erste dieser drei Typen, in der der Wert der Konstante dargestellt werden kann, ist der Typ, der der Konstante zugewiesen wird.  
  
-   Je nach Größe der Konstanten wird der Typ `int`, `unsigned int`, **long int** oder **unsigned long int** den Oktal\- und Hexadezimalkonstanten ohne Suffixe zugewiesen.  
  
-   Je nach Größe der Konstanten wird der Typ **unsigned int** oder **unsigned long int** den Konstanten mit einem **u**\- oder **U**\-Suffix zugewiesen.  
  
-   Je nach Größe der Konstanten wird der Typ **long int** oder **unsigned long int** den Konstanten mit dem **l**\- oder **L**\-Suffix zugewiesen.  
  
-   Konstanten mit einem **u**\- oder **U**\- und einem **l**\- oder **L**\-Suffix wird der Typ **unsigned long int** zugewiesen.  
  
## Siehe auch  
 [C\-Ganzzahlkonstanten](../c-language/c-integer-constants.md)