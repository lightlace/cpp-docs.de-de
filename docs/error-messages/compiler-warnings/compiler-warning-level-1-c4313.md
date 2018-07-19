---
title: Compilerwarnung (Stufe 1) C4313 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4313
dev_langs:
- C++
helpviewer_keywords:
- C4313
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e42bd8f19ac9a70f93a26265af6e310fb51e7229
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283938"
---
# <a name="compiler-warning-level-1-c4313"></a>Compilerwarnung (Stufe 1) C4313
'Funktion': 'Formatbezeichner' in der Formatzeichenfolge steht mit der Argumentennummer vom Typ 'Typ' in Konflikt.  
  
 Es besteht ein Konflikt zwischen dem angegebenen Format und dem Wert, den Sie übergeben. Beispielsweise haben Sie einen 64-Bit-Parameter an einen nicht qualifizierten Formatbezeichner „%d“ übergeben, wohingegen ein 32-Bit-Ganzzahl-Parameter erwartet wird. Diese Warnung ist nur aktiv, wenn der Code für 64-Bit-Ziele kompiliert wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird C4313 generiert, wenn dies für 64-Bit-Ziele kompiliert wird.  
  
```  
// C4313.cpp  
// Compile by using: cl /W1 C4313.cpp  
#include <stdio.h>  
int main() {  
   int * pI = 0;  
   printf("%d", pI);   // C4313 on 64-bit platform code  
   // Try one of the following lines instead:  
   // printf("%p\n", pI);  
   // printf("%Id\n", pI);   // %I64d expects 64-bits of information  
}  
```