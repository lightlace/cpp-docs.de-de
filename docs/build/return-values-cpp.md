---
title: "Rückgabewerte (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 53583524-b337-4228-a9c6-c9bf516babe8
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8f8ac22790fa6b94dd19ba7d46cf737824e898f1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="return-values-c"></a>Rückgabewerte (C++)
Ein skalarer Rückgabewert, der in 64 Bits passt, wird durch RAX zurückgegeben, dazu gehören auch __m64-Typen. Nicht skalare Typen, darunter Gleitkommazahlen, Doubles und vektortypen, wie z. B. [__m128](../cpp/m128.md), [__m128i](../cpp/m128i.md), [__m128d](../cpp/m128d.md) werden in XMM0 zurückgegeben. Der Status von nicht verwendeten Bits in dem in RAX oder XMM0 zurückgegebenen Wert ist nicht definiert.  
  
 Benutzerdefinierte Typen können als Wert von globalen Funktionen und statische Memberfunktionen zurückgegeben werden. Um als Wert in RAX zurückgegeben zu werden, müssen benutzerdefinierte Typen eine Länge von 1, 2, 4, 8, 16, 32 oder 64 Bits haben; keinen benutzerdefinierten Konstruktor, Destruktor oder Kopierzuweisungsoperator; keine privaten oder geschützten nicht statischen Datenmember; keine nicht statischen Datenmember vom Typ Verweis; keine Basisklassen; keine virtuellen Funktionen; und keine Datenmember, die diese Anforderungen nicht ebenfalls erfüllen. (Dies ist im Grunde die Definition eines C++03 POD-Typs. Da die Definition im Standard C++11 geändert wurde, sollte `std::is_pod` nicht für diesen Test verwendet werden.) Andernfalls nimmt der Aufrufer die Verantwortung für die Speicherbelegung und für die Übergabe eines Zeigers für den Rückgabewert als erstes Argument an. Nachfolgende Argumente werden dann um ein Argument nach rechts verschoben. Derselbe Zeiger muss vom Aufgerufenen in RAX zurückgegeben werden.  
  
 Diese Beispiele zeigen, wie Parameter und Rückgabewerte für Funktionen mit den angegebenen Deklarationen übergeben werden:  
  
## <a name="example-of-return-value-1---64-bit-result"></a>Beispiel für Rückgabewert 1 64-Bit-Ergebnis  
  
```Output  
__int64 func1(int a, float b, int c, int d, int e);  
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,  
// callee returns __int64 result in RAX.  
```  
  
## <a name="example-of-return-value-2---128-bit-result"></a>Beispiel für Rückgabewert 2-128-Bit-Ergebnis  
  
```Output  
__m128 func2(float a, double b, int c, __m64 d);   
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,   
// callee returns __m128 result in XMM0.  
```  
  
## <a name="example-of-return-value-3---user-type-result-by-pointer"></a>Beispiel für Rückgabewert 3 – Ergebnis Benutzertyp als Zeiger  
  
```Output  
struct Struct1 {  
   int j, k, l;    // Struct1 exceeds 64 bits.   
};  
Struct1 func3(int a, double b, int c, float d);   
// Caller allocates memory for Struct1 returned and passes pointer in RCX,   
// a in RDX, b in XMM2, c in R9, d pushed on the stack;   
// callee returns pointer to Struct1 result in RAX.  
```  
  
## <a name="example-of-return-value-4---user-type-result-by-value"></a>Beispiel für Rückgabewert 4 – Ergebnis Benutzertyp als Wert  
  
```Output  
struct Struct2 {  
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.  
};  
Struct2 func4(int a, double b, int c, float d);   
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;   
// callee returns Struct2 result by value in RAX.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)