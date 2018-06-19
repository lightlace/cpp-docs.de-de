---
title: __noop | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __noop_cpp
- __noop
dev_langs:
- C++
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14d7ab3f1a61dc0644bf5683376ac676fbfcd6b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322613"
---
# <a name="noop"></a>__noop
**Microsoft-spezifisch**  
  
 Die `__noop` systeminterne gibt an, dass eine Funktion ignoriert werden sollen und die Argumentliste analysiert werden, jedoch kein Code generiert werden, für die Argumente. Es dient zur Verwendung in globalen Debugfunktionen, die eine Variable Anzahl von Argumenten akzeptieren.  
  
 Der Compiler konvertiert die `__noop` systeminterne 0 zum Zeitpunkt der Kompilierung.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie verwenden konnten `__noop`.  
  
```  
// compiler_intrinsics__noop.cpp  
// compile with or without /DDEBUG  
#include <stdio.h>  
  
#if DEBUG  
   #define PRINT   printf_s  
#else  
   #define PRINT   __noop  
#endif  
  
int main() {  
   PRINT("\nhello\n");  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)