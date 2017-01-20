---
title: "function (C/C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "function_CPP"
  - "vc-pragma.function"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "function-Pragma"
  - "Pragmas, Funktion"
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# function (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass Funktionsaufrufe generiert werden, die in der Argumentliste des Pragmas angegeben sind.  
  
## Syntax  
  
```  
  
#pragma function( function1 [, function2, ...] )  
```  
  
## Hinweise  
 Wenn Sie das **intrinsic**\-Pragma \(oder \/Oi\) verwenden, um den Compiler aufzufordern, systeminterne Funktionen zu generieren \(systeminterne Funktionen werden als Inlinecode und nicht als Funktionsaufrufe generiert\), können Sie das **function**\-Pragma verwenden, um einen Funktionsaufruf explizit zu erzwingen.  Sobald ein function\-Pragma angezeigt wird, tritt es mit der ersten Funktionsdefinition in Kraft, die eine bestimmte systeminterne Funktion enthält.  Die Wirkung dauert bis zum Ende der Quelldatei oder bis zum Auftreten eines **intrinsic**\-Pragmas, das die gleiche systeminterne Funktion angibt.  Das **function**\-Pragma kann nur außerhalb einer Funktion auf globaler Ebene verwendet werden.  
  
 Listen der Funktionen mit systeminternen Formen finden Sie unter [\#pragma intrinsic](../preprocessor/intrinsic.md).  
  
## Beispiel  
  
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
  
  **str lautet 'Now\*\*\*\*\*\*\*\*\*\*\*\*'**  
**str lautet '\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!'**   
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)