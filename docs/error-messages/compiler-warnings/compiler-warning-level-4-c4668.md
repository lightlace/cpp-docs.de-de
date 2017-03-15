---
title: "Compilerwarnung (Stufe 4) C4668 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4668"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4668"
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 4) C4668
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol' ist nicht als ein Präprozessormakro definiert, wird durch '0' für 'Direktiven' ersetzt  
  
 Mit einer Präprozessordirektive wurde ein nicht definiertes Symbol verwendet.  Das Symbol wird mit false ausgewertet.  Ein Symbol kann entweder mit der [\#define\-Direktive](../../preprocessor/hash-define-directive-c-cpp.md) oder mit der Compileroption [\/D](../../build/reference/d-preprocessor-definitions.md) definiert werden.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4668 generiert:  
  
```  
// C4668.cpp  
// compile with: /W4  
#include <stdio.h>  
  
#pragma warning (default : 4668)   // turn warning on  
  
int main()   
{  
    #if q   // C4668, q is not defined  
        printf_s("defined");  
    #else  
        printf_s("undefined");  
    #endif  
}  
```