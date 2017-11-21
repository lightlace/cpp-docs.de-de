---
title: _heapchk | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _heapchk
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _heapchk
- heapchk
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- consistency checking of heaps
- heapchk function
- heaps, checking consistency
- _heapchk function
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9fcbafbb98385878dbc84f300e8d2bf0dac581c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="heapchk"></a>_heapchk
Führt Konsistenzüberprüfungen auf dem Heap aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _heapchk( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `_heapchk` gibt eine der folgenden ganzzahligen Manifestkonstanten zurück, die in Malloc.h definiert sind.  
  
 `_HEAPBADBEGIN`  
 Die ursprüngliche Headerinformation ist schlecht oder wurde nicht gefunden.  
  
 `_HEAPBADNODE`  
 Ein ungültiger Knoten wurde gefunden, oder Heap ist beschädigt.  
  
 `_HEAPBADPTR`  
 Der Zeiger auf einen Heap ist ungültig.  
  
 `_HEAPEMPTY`  
 Der Heap wurde noch nicht initialisiert.  
  
 `_HEAPOK`  
 Der Heap scheint konsistent zu sein.  
  
 Wenn ein Fehler auftritt, setzt `_heapchk``errno` zudem auf `ENOSYS`.  
  
## <a name="remarks"></a>Hinweise  
 Die `_heapchk`-Funktion hilft, Heap-bezogene Probleme zu debuggen, indem auf minimale Konsistenz des Heaps gesucht wird. Wenn das Betriebssystem nicht `_heapchk` unterstützt (beispielsweise Windows 98), gibt die Funktion `_HEAPOK` zurück und legt `errno` auf `ENOSYS` fest.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_heapchk`|\<malloc.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_heapchk.c  
// This program checks the heap for  
// consistency and prints an appropriate message.  
  
#include <malloc.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  heapstatus;  
   char *buffer;  
  
   // Allocate and deallocate some memory  
   if( (buffer = (char *)malloc( 100 )) != NULL )  
      free( buffer );  
  
   // Check heap status  
   heapstatus = _heapchk();  
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf(" OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf(" OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
}  
```  
  
```Output  
OK - heap is fine  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [_heapadd](../../c-runtime-library/heapadd.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_heapset](../../c-runtime-library/heapset.md)   
 [_heapwalk](../../c-runtime-library/reference/heapwalk.md)