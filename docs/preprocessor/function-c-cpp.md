---
title: -Funktion (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- function_CPP
- vc-pragma.function
dev_langs:
- C++
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b6f83e92cdcfe6434c99497a9eddf496027798f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="function-cc"></a>function (C/C++)
Gibt an, dass Funktionsaufrufe generiert werden, die in der Argumentliste des Pragmas angegeben sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma function( function1 [, function2, ...] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Bei Verwendung der **systeminterne** Pragma (oder/Oi) um den Compiler aufzufordern, systeminterne Funktionen generieren (systeminterne Funktionen werden als Inlinecode und nicht als Funktionsaufrufe generiert), können Sie die **Funktion** Pragma Um einen Funktionsaufruf explizit zu erzwingen. Sobald ein function-Pragma angezeigt wird, tritt es mit der ersten Funktionsdefinition in Kraft, die eine bestimmte intrinsische Funktion enthält. Die Wirkung dauert bis an das Ende der Quelldatei oder bis zum Auftreten einer **systeminterne** Pragmas, die die gleiche intrinsische Funktion angibt. Die **Funktion** Pragma kann nur außerhalb einer Funktion verwendet werden – auf globaler Ebene.  
  
 Listen der Funktionen mit systeminternen Formen finden Sie unter [#pragma intrinsic](../preprocessor/intrinsic.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// pragma_directive_function.cpp  
#include <ctype.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
  
// use intrinsic forms of memset and strlen  
#pragma intrinsic(memset, strlen)  
  
// Find first word break in string, and set remaining  
// chars in string to specified char value.  
char *set_str_after_word(char *string, char ch) {  
   int i;  
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */  
  
   for(i = 0; i < len; i++) {  
      if (isspace(*(string + i)))   
         break;  
   }  
  
   for(; i < len; i++)   
      *(string + i) = ch;  
  
   return string;  
}  
  
// do not use strlen intrinsic  
#pragma function(strlen)  
  
// Set all chars in string to specified char value.  
char *set_str(char *string, char ch) {  
   // Uses intrinsic for memset, but calls strlen library function  
   return (char *) memset(string, ch, strlen(string));  
}  
  
int main() {  
   char *str = (char *) malloc(20 * sizeof(char));  
  
   strcpy_s(str, sizeof("Now is the time"), "Now is the time");  
   printf("str is '%s'\n", set_str_after_word(str, '*'));  
   printf("str is '%s'\n", set_str(str, '!'));  
}  
```  
  
```Output  
str is 'Now************'  
str is '!!!!!!!!!!!!!!!'  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)