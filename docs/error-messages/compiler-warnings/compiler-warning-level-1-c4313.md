---
title: Compilerwarnung (Stufe 1) C4313 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4313
dev_langs: C++
helpviewer_keywords: C4313
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1b90fe384ac3396e73eb2fc69aab3a6d48552adf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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