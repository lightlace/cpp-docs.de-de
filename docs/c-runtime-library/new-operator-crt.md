---
title: "operator new(CRT)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "new[]"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "operator new[]"
  - "vector new"
ms.assetid: 79682f85-6889-40f6-b8f7-9eed5176ea35
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# operator new(CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zuordnen Speicherblock im Heap zu  
  
## Syntax  
  
```  
  
      void *__cdecl operator new[](size_t count);  
void *__cdecl operator new[] (  
   size_t count,   
   void * object  
) throw();  
void *__cdecl operator new[] (  
   size_t count,   
   const std::nothrow_t&  
) throw();  
```  
  
#### Parameter  
 *count*  
 Die Größe der Speicherbelegung.  
  
 *Objekt*  
 Ein Zeiger auf einen Speicherblock, in dem das Objekt erstellt wird.  
  
## Rückgabewert  
 Ein Zeiger zur niedrigsten Byteadresse des neu reserviertes Speicher.  
  
## Hinweise  
 Dieses Formular von `operator new` werden als neuer Vektor, im Gegensatz zum skalaren neuen Formular \([Operator neu](../c-runtime-library/operator-new-crt.md)\).  
  
 Das erste Formular dieses Operators wird als das nonplacement Formular.  Das zweite Format dieses Operators bezeichnet, da die Positionierungsform und das dritte Formular dieses Operators nonthrowing die Positionierungsform ist.  
  
 Das erste Formular des Operators wird vom Compiler definiert und nicht new.h erfordert, im Programm eingefügt werden.  
  
 [Operator delete&#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md) gibt den Arbeitsspeicher frei, der mit dem Operator new zugeordnet ist.  
  
 Sie können konfigurieren, ob `operator new[]` gibt NULL oder lösen eine Ausnahme auf Fehler aus.  Weitere Informationen finden Sie unter [Die Operatoren new und delete](../cpp/new-and-delete-operators.md).  
  
 Mit Ausnahme von auslösendem oder NO\-auslösendem Verhalten verhält sich das CRT `operator new` wie [Operator new&#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) in der C\+\+\-Standardbibliothek.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`new[]`|\<new.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Im Folgenden wird gezeigt, wie die vektorielle, nicht außerhalb Form von `operator new` verwendet.  
  
```  
// crt_new4.cpp  
#include <stdio.h>  
int main() {  
   int * k = new int[10];  
   k[0] = 21;  
   printf("%d\n", k[0]);  
   delete [] k;  
}  
```  
  
 Im Folgenden wird gezeigt, wie die vektorielle Positionierungsform von `operator new` verwendet.  
  
```  
// crt_new5.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * i = new int[10];  
   i[0] = 21;  
   printf("%d\n", i[0]);  
   // initialize existing memory (i) with, in this case, int[[10]  
   int * j = new(i) int[10];   // placement vector new  
   printf("%d\n", j[0]);  
   j[0] = 22;  
   printf("%d\n", i[0]);  
   delete [] i;   // or, could have deleted [] j   
}  
```  
  
 Im Folgenden wird gezeigt, wie den Vektor, Platzierung, NO\-THROW\-Formular von `operator new` verwendet.  
  
```  
// crt_new6.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * k = new(std::nothrow) int[10];  
   k[0] = 21;  
   printf("%d\n", k[0]);  
   delete [] k;  
}  
```  
  
## Siehe auch  
 [Speicherbelegung](../c-runtime-library/memory-allocation.md)