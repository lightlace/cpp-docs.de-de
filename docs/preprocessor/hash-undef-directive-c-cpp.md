---
title: "#undef-Direktive (C/C++)"
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
  - "#undef"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#undef-Direktive"
  - "Präprozessor, Direktiven"
  - "undef-Direktive (#undef)"
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# #undef-Direktive (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Entfernt einen Namen, der zuvor mit `#define` erstellt wurde \(hebt die Definierung auf\).  
  
## Syntax  
  
```  
  
#undef   
identifier  
  
```  
  
## Hinweise  
 Die `#undef`\-Direktive entfernt die aktuelle Definition vom *identifier*.  Folglich werden die nächsten Vorkommen vom *identifier* vom Präprozessor ignoriert.  Um eine Makrodefinition mithilfe von `#undef` zu entfernen, geben Sie nur den *identifier*  des Makros an, keine Parameterliste.  
  
 Sie können die `#undef`\-Direktive auch auf einen Bezeichner anwenden, der keine vorherige Definition hat.  Dadurch wird sichergestellt, dass der Bezeichner nicht definiert wird.  Innerhalb von `#undef`\-Anweisungen wird keine Makroersetzung durchgeführt.  
  
 Die `#undef`\-Direktiven werden in der Regel paarweise mit `#define`\-Direktiven verwendet, um einen Bereich in einem Quellprogramm zu erstellen, in dem ein Bezeichner eine besondere Bedeutung hat.  Beispielsweise kann eine bestimmte Funktion des Quellprogramms Manifestkonstanten verwenden, um umgebungsspezifische Werte zu definieren, die sich nicht auf das übrige Programm auswirken.  Die `#undef`\-Direktive kann auch zusammen mit der `#if`\-Direktive eine bedingte Kompilierung des Quellprogramms steuern.  Weitere Informationen finden Sie unter [\#if\-, \#elif\-, \#else\- und \#endif\-Direktiven](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
 Im folgenden Beispiel entfernt die `#undef`\-Direktive die Definitionen einer symbolischen Konstante und eines Makros.  Beachten Sie, dass nur der Bezeichner des Makros angegeben wird.  
  
```  
#define WIDTH 80  
#define ADD( X, Y ) ((X) + (Y))  
.  
.  
.  
#undef WIDTH  
#undef ADD  
```  
  
 **Microsoft\-spezifisch**  
  
 Die Definition für Makros kann in der Befehlszeile mithilfe der "\/U"\-Option, gefolgt von den gewünschten Makronamen, aufgehoben werden.  Die Auswirkungen dieses Befehls entsprechen einer Sequenz von `#undef` *macro\-name*\-Anweisungen am Anfang der Datei.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)