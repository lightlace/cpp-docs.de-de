---
title: "operator new (CRT)"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "operator new"
  - "Skalar neu"
ms.assetid: 4ae51618-a4e6-4172-b324-b99d86d1bdca
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# operator new (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ordnet Speicherblock im Heap zu  
  
## Syntax  
  
```  
  
      void *__cdecl operator new(  
   size_t count  
);  
void *__cdecl operator new(  
   size_t count,   
   void * object  
) throw();  
void *__cdecl operator new(  
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
 Dieses Formular von `operator new` wird als skalares neues, im Gegensatz zu dem neuen Formular des Vektors \([Operator new&#91;&#93;](../c-runtime-library/new-operator-crt.md)\).  
  
 Das erste Formular dieses Operators wird als das nonplacement Formular.  Das zweite Format dieses Operators bezeichnet, da die Positionierungsform und das dritte Formular dieses Operators nicht die auslösende Positionierungsform ist.  
  
 Das erste Formular des Operators wird vom Compiler definiert und nicht new.h erfordert, im Programm eingefügt werden.  
  
 [Operator](../c-runtime-library/operator-delete-crt.md) gibt den Arbeitsspeicher frei, der `operator new` zugeordnet ist.  
  
 Sie können konfigurieren, ob neue Operator gibt NULL oder lösen eine Ausnahme auf Fehler aus.  Weitere Informationen finden Sie unter [Die Operatoren new und delete](../cpp/new-and-delete-operators.md).  
  
 Mit Ausnahme von auslösendem oder NO\-auslösendem Verhalten verhält sich das CRT `operator new` wie [Operator neu](../Topic/operator%20new%20\(%3Cnew%3E\).md) in der C\+\+\-Standardbibliothek.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|**new**|\<new.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Im Folgenden wird gezeigt, wie Skalar, nonplacement Formular von `operator new` verwendet.  
  
```  
// crt_new1.cpp  
#include <stdio.h>  
int main() {  
   int * i = new int(6);  
   printf("%d\n", *i);  
   delete i;  
}  
```  
  
 Im Folgenden wird gezeigt, wie die skalare Positionierungsform von `operator new` verwendet.  
  
```  
// crt_new2.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * i = new int(12);  
   printf("*i = %d\n", *i);  
   // initialize existing memory (i) with, in this case, int(7)  
   int * j = new(i) int(7);   // placement new  
   printf("*j = %d\n", *j);  
   printf("*i = %d\n", *i);  
   delete i;   // or, could have deleted j  
}  
```  
  
 Im Folgenden wird gezeigt, wie Skalar, Platzierung, NO\-THROW\-Formular von `operator new` verwendet.  
  
```  
// crt_new3.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   // allocates memory, initialize (8) and if call fails, new returns null  
   int * k = new(std::nothrow) int(8);   // placement new  
   printf("%d\n", *k);  
   delete k;  
}  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../c-runtime-library/memory-allocation.md)