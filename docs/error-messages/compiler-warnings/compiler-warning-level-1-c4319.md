---
title: Compilerwarnung (Stufe 1) C4319 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4319
dev_langs: C++
helpviewer_keywords: C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dded592ef5b82329725937c40584d889d5aeb249
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4319"></a>Compilerwarnung (Stufe 1) C4319
'operator': Mit 0 erweitert von 'type' zu größerem 'type'  
  
 Das Ergebnis des ~-Operators (bitweises Komplement) ist nicht signiert und wird anschließend mit 0 erweitert, wenn es zu einem größeren Typ konvertiert wird.  
  
 Im folgenden Beispiel wird ~(a - 1) als ein nicht signierter, langer 32-Bit-Ausdruck ausgewertet und anschließend durch die Erweiterung mit 0 zu 64 Bit konvertiert. Dies kann zu unerwarteten Vorgangsergebnisse führen.  
  
```  
// C4319.cpp  
// compile with: cl /W4 C4319.cpp  
int main() {  
   unsigned long a = 0;  
   unsigned long long q = 42;  
   q = q & ~(a - 1);    // C4319 expected  
}  
```