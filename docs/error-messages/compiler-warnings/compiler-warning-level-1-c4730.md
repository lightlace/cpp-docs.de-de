---
title: "Compilerwarnung (Stufe 1) C4730 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4730"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4730"
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4730
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'main' : Das Kombinieren von \_m64 und Gleitkommaausdrücken kann zu fehlerhaftem Code führen  
  
 Eine Funktion verwendet [\_\_m64](../../cpp/m64.md) und den Typ **float**\/**double**.  Da die MMX\- und Gleitkommaregister denselben physischen Registerbereich nutzen \(die gleichzeitige Verwendung ist nicht möglich\), kann die Verwendung von `__m64` und der Typen **float**\/**double** in derselben Funktion zu fehlerhaften Daten und folglich zu einer Ausnahme führen.  
  
 Um `__m64`\-Typen und Gleitkommatypen problemlos verwenden arbeiten identisch, jede Anweisung die einen dieser Typen von **\_m\_empty\(\)** \(für MMX\) oder systeminterne Funktion **\_m\_femms\(\)** \(für 3DNow\!\).  
  
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