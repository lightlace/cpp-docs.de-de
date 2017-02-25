---
title: "Pr&#228;prozessoroperatoren | Microsoft Docs"
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
  - "Operatoren [C++], Präprozessor"
  - "Präprozessoroperatoren"
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Pr&#228;prozessoroperatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vier präprozessorspezifische Operatoren werden im Kontext der `#define`\-Direktive verwendet \(die jeweilige Zusammenfassung finden Sie in der nachfolgenden Liste\).  Zeichenfolgenoperatoren, Zeichenoperatoren und Operatoren zum Einfügen eines Tokens werden in den nächsten drei Abschnitten erläutert.  Weitere Informationen zum **defined**\-Operator finden Sie unter [Die Direktiven \#if, \#elif, \#else und \#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
|Operator|Aktion|  
|--------------|------------|  
|[Zeichenfolgenoperator \(\#\)](../preprocessor/stringizing-operator-hash.md)|Bewirkt, dass das entsprechende tatsächliche Argument in doppelte Anführungszeichen eingeschlossen wird.|  
|[Zeichenoperator \(\#@\)](../preprocessor/charizing-operator-hash-at.md)|Bewirkt, dass das entsprechende Argument in einfache Anführungszeichen eingeschlossen und als Zeichen behandelt wird \(Microsoft\-spezifisch\).|  
|[Operator zum Einfügen eines Tokens \(\#\#\)](../preprocessor/token-pasting-operator-hash-hash.md)|Ermöglicht das Verketten der Token, die als tatsächliche Argumente verwendet werden, um andere Token zu bilden.|  
|[Definierter Operator](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Vereinfacht das Schreiben von zusammengesetzten Ausdrücken in bestimmten Makrodirektiven.|  
  
## Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)   
 [Vordefinierte Makros](../preprocessor/predefined-macros.md)   
 [C\/C\+\+\-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)