---
title: "calloc"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "calloc"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "calloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Speicherbelegung, Arrays"
  - "calloc-Funktion"
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# calloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ordnet ein Array im Arbeitsspeicher mit den Elementen zu, die auf 0 initialisiert werden.  
  
## Syntax  
  
```  
void *calloc(   
   size_t num,  
   size_t size   
);  
```  
  
#### Parameter  
 `num`  
 Anzahl der Elemente.  
  
 `size`  
 Länge in Bytes jedes Elements.  
  
## Rückgabewert  
 `calloc` gibt einen Zeiger auf den reservierten Platz zurück.  Der Speicherplatz, der auf den mit dem Rückgabewert gezeigt wird, wird sichergestellt, zum Speichern eines beliebigen Typs Objekt ordnungsgemäß ausgerichtet sind.  Um einen Zeiger auf einen anderen Typ als `void` zu erhalten, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
## Hinweise  
 Die `calloc` ordnet Funktion Speicherplatz für ein `num` \- Array Elemente, Länge jedes von Bytes `size` zu.  Jedes Element wird 0 initialisiert.  
  
 `calloc` setzt `errno` auf `ENOMEM`, wenn eine Speicherbelegung fehlschlägt oder wenn der benötigte Speicherplatz größer ist als `_HEAP_MAXREQ`.  Informationen hierzu und andere Fehlercodes, finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `calloc` Ruft `malloc` auf, um der Funktion C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) verwenden, um den neuen Handlermodus festzulegen.  Der neue Handlermodus gibt an, ob bei einem Fehler `malloc` die neue Handlerroutine aufgerufen werden soll, wie dies von [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md) festgelegt ist.  Standardmäßig ruft `malloc` bei einem Speicherbelegungsfehler nicht die neue Handlerroutine auf.  Sie können dieses Standardverhalten überschreiben, sodass, wenn `calloc` Speicher nicht belegen kann,`malloc` die neue Handlerroutine genauso aufruft wie der `new`\-Operator, wenn dieser aus demselben Grund fehlschlägt.  Um den Standardwert zu überschreiben, rufen Sie  
  
```  
_set_new_mode(1)  
```  
  
 rechtzeitig im Programm auf oder stellen eine Verknüpfung mit NEWMODE.OBJ \(siehe [Linkoptionen](../../c-runtime-library/link-options.md)\) her.  
  
 Wenn die Anwendung mit einer Debugversion der C\-Laufzeitbibliotheken verknüpft ist, wird `calloc` von [\_calloc\_dbg](../../c-runtime-library/reference/calloc-dbg.md) auf.  Weitere Informationen dazu, wie der Heap während des Debuggingsprozesses verwaltet wird, finden Sie unter [Der CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `calloc` ist als `__declspec(noalias)` gekennzeichnet und `__declspec(restrict)` heißt, dass die Funktion, die gewährleistet sind globale Variablen nicht zu ändern und der zurückgegebene Zeiger nicht von Alias\-.  Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [Einschränken ein](../../cpp/restrict.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`calloc`|\<stdlib.h\> und \<malloc.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_calloc.c  
// This program uses calloc to allocate space for  
// 40 long integers. It initializes each element to zero.  
  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   long *buffer;  
  
   buffer = (long *)calloc( 40, sizeof( long ) );  
   if( buffer != NULL )  
      printf( "Allocated 40 long integers\n" );  
   else  
      printf( "Can't allocate memory\n" );  
   free( buffer );  
}  
```  
  
  **Zugeordnet 40 lange ganze Zahlen**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)