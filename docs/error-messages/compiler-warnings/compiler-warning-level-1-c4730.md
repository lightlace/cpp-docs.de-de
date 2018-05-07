---
title: Compilerwarnung (Stufe 1) C4730 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4730
dev_langs:
- C++
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 467d9fd04e2fef78d480fc4db1417b6e4c8d5641
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4730"></a>Compilerwarnung (Stufe 1) C4730
'main': Kombinieren von _m64 und Ausdrücke möglicherweise falsche Code führen  
  
 Eine Funktion verwendet [__m64](../../cpp/m64.md) und **"float"**/**doppelte** Typen. Da die MMX- und Gleitkommaregister denselben physischen Speicherplatz zu registrieren (kann nicht gleichzeitig verwendet werden), mit `__m64` und **"float"**/**doppelte** Typen in der gleichen Funktion kann dazu führen, dass Daten beschädigt, möglicherweise eine Ausnahme auszulösen.  
  
 Zum sicheren verwenden `__m64` Typen und Gleitkommatypen in derselben Funktion sollte jede Anweisung, die einen der Typen verwendet getrennt werden, durch die **_m_empty()** (für MMX) oder **_m_femms()** (für 3DNow!) systeminterne Funktion.  
  
 Im folgenden Beispiel wird C4730 generiert:  
  
```  
// C4730.cpp  
// compile with: /W1  
// processor: x86  
#include "mmintrin.h"  
  
void func(double)  
{  
}  
  
int main(__m64 a, __m64 b)  
{  
   __m64 m;  
   double f;  
   f = 1.0;  
   m = _m_paddb(a, b);  
   // uncomment the next line to resolve C4730  
   // _m_empty();  
   func(f * 3.0);   // C4730  
}  
```