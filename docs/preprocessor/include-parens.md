---
title: "include()"
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
  - "include()"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "include()-Attribut"
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# include()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Deaktiviert den automatische Ausschluss.  
  
## Syntax  
  
```  
include("Name1"[,"Name2", ...])  
```  
  
#### Parameter  
 `Name1`  
 Das erste Element, dessen Aufnahme erzwungen wird.  
  
 `Name2`  
 Das zweite Element, dessen Aufnahme erzwungen wird \(falls erforderlich\).  
  
## Hinweise  
 Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind.  `#import` versucht, mehrfache Definitionsfehler dadurch zu vermeiden, dass solche Elemente automatisch ausgeschlossen werden.  Wenn Elemente ausgeschlossen wurden, wie von [Compilerwarnung \(Stufe 3\) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) angegeben, aber nicht ausgeschlossen sein sollen, kann dieses Attribut verwendet werden, um den automatischen Ausschluss zu deaktivieren.  Dieses Attribut kann eine beliebige Anzahl von Argumenten akzeptieren, die jeweils der Name des einzuschließenden Typbibliothekelements sind.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)