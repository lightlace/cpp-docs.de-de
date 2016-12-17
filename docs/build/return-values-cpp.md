---
title: "R&#252;ckgabewerte (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 53583524-b337-4228-a9c6-c9bf516babe8
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# R&#252;ckgabewerte (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein skalarer Rückgabewert, der in 64 Bits passt, wird durch RAX zurückgegeben, dazu gehören auch \_\_m64\-Typen.  Nicht skalare Typen, darunter Gleitkommazahlen, Doubles und Vektortypen, wie z. B. [\_\_m128](../cpp/m128.md), [\_\_m128i](../cpp/m128i.md), [\_\_m128d](../cpp/m128d.md), werden in XMM0 zurückgegeben.  Der Status von nicht verwendeten Bits in dem in RAX oder XMM0 zurückgegebenen Wert ist nicht definiert.  
  
 Benutzerdefinierte Typen können als Wert von globalen Funktionen und statische Memberfunktionen zurückgegeben werden.  Um als Wert in RAX zurückgegeben zu werden, müssen benutzerdefinierte Typen eine Länge von 1, 2, 4, 8, 16, 32 oder 64 Bits haben; keinen benutzerdefinierten Konstruktor, Destruktor oder Kopierzuweisungsoperator; keine privaten oder geschützten nicht statischen Datenmember; keine nicht statischen Datenmember vom Typ Verweis; keine Basisklassen; keine virtuellen Funktionen; und keine Datenmember, die diese Anforderungen nicht ebenfalls erfüllen.  \(Dies ist im Grunde die Definition eines C\+\+03 POD\-Typs.  Da die Definition im Standard C\+\+11 geändert wurde, sollte `std::is_pod` nicht für diesen Test verwendet werden.\) Andernfalls nimmt der Aufrufer die Verantwortung für die Speicherbelegung und für die Übergabe eines Zeigers für den Rückgabewert als erstes Argument an.  Nachfolgende Argumente werden dann um ein Argument nach rechts verschoben.  Derselbe Zeiger muss vom Aufgerufenen in RAX zurückgegeben werden.  
  
 Diese Beispiele zeigen, wie Parameter und Rückgabewerte für Funktionen mit den angegebenen Deklarationen übergeben werden:  
  
## Beispiel für Rückgabewert 1 – Ergebnis 64 Bit  
  **\_\_int64 func1\(int a, float b, int c, int d, int e\);**  
**\/\/ Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,**  
**\/\/ callee returns \_\_int64 result in RAX.**   
## Beispiel für Rückgabewert 2 – Ergebnis 128 Bit  
  **\_\_m128 func2\(float a, double b, int c, \_\_m64 d\);**   
**\/\/ Caller passes a in XMM0, b in XMM1, c in R8, d in R9,**   
**\/\/ callee returns \_\_m128 result in XMM0.**   
## Beispiel für Rückgabewert 3 – Ergebnis Benutzertyp als Zeiger  
  **struct Struct1 {**  
 **int j, k, l;    \/\/ Struct1 exceeds 64 bits.  };**  
**Struct1 func3\(int a, double b, int c, float d\);**   
**\/\/ Caller allocates memory for Struct1 returned and passes pointer in RCX,**   
**\/\/ a in RDX, b in XMM2, c in R9, d pushed on the stack;**   
**\/\/ callee returns pointer to Struct1 result in RAX.**    
## Beispiel für Rückgabewert 4 – Ergebnis Benutzertyp als Wert  
  **struct Struct2 {**  
 **int j, k;    \/\/ Struct2 fits in 64 bits, and meets requirements for return by value.  };**  
**Struct2 func4\(int a, double b, int c, float d\);**   
**\/\/ Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;**   
**\/\/ callee returns Struct2 result by value in RAX.**    
## Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)