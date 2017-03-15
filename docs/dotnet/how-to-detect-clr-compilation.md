---
title: "Gewusst wie: Erkennen der /clr-Kompilierung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr-Compileroption [C++], Erkennen der Verwendung von"
  - "Kompilierung, Erkennen von /clr"
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Gewusst wie: Erkennen der /clr-Kompilierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie das `_MANAGED`\-Makro oder das `_M_CEE`\-Makro, um zu ermitteln, ob ein Modul mit **\/clr**kompiliert wird.  Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Weitere Informationen über Makros finden Sie unter [Vordefinierte Makros](../preprocessor/predefined-macros.md).  
  
## Beispiel  
  
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
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)