---
title: Compilerfehler C2472 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2472
dev_langs:
- C++
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d89a6d6b10fa76c7fbf1bf11c4ebe2ecff5f98ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2472"></a>Compilerfehler C2472
"function" kann nicht in verwaltetem Code generiert werden: "message". Kompilieren Sie mit /clr, um ein gemischtes Image zu generieren  
  
 Dieser Fehler tritt auf, wenn von verwaltetem Code nicht unterstützte Typen innerhalb einer reinen CLR-Umgebung (Common Language Runtime) verwendet werden. Kompilieren Sie mit **/clr** , um den Fehler zu beheben.  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2472 generiert.  
  
```  
// C2472.cpp  
// compile with: /clr:pure  
// C2472 expected  
  
#include <cstdlib>  
  
int main()  
{  
   int * __ptr32 p32;  
   int * __ptr64 p64;  
  
   p32 = (int * __ptr32)malloc(4);  
   p64 = p32;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)