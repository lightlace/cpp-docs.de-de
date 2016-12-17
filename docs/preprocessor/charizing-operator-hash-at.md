---
title: "Zeichenoperator (#@)"
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
  - "#@"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#@-Präprozessoroperator"
  - "Zeichenoperator"
  - "Präprozessor, Operatoren"
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Zeichenoperator (#@)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Der Zeichenoperator kann nur mit Argumenten von Makros verwendet werden.  Wenn **\#@** vor einem formalen Parameter in der Definition des Makros steht, wird das tatsächliche Argument in einfache Anführungszeichen eingeschlossen und als Zeichen behandelt, wenn das Makro erweitert wird.  Beispiel:  
  
```  
#define makechar(x)  #@x  
```  
  
 führt dazu, dass die Anweisung  
  
```  
a = makechar(b);  
```  
  
 erweitert wird auf  
  
```  
a = 'b';  
```  
  
 Das einfache Anführungszeichen kann nicht mit dem Zeichenoperator verwendet werden.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)