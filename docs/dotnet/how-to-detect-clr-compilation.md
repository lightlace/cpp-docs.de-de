---
title: 'Vorgehensweise: Erkennen von Clr - Kompilierung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- compilation, detecting /clr
- /clr compiler option [C++], detecting use of
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 51fa6b5e222b980bdf3a8757434f1caaed0085c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-detect-clr-compilation"></a>Gewusst wie: Erkennen der /clr-Kompilierung
Verwenden der `_MANAGED` oder `_M_CEE` Makro, um festzustellen, ob ein Modul mit lieg **"/ CLR"**. Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Weitere Informationen zu Makros finden Sie unter [vordefinierte Makros](../preprocessor/predefined-macros.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// detect_CLR_compilation.cpp  
// compile with: /clr  
#include <stdio.h>  
  
int main() {  
   #if (_MANAGED == 1) || (_M_CEE == 1)  
      printf_s("compiling with /clr\n");  
   #else  
      printf_s("compiling without /clr\n");  
   #endif  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)