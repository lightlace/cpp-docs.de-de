---
title: calloc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- calloc
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
- calloc
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 574d1e8a48de3aa380b6d51ba71c28a953572013
ms.lasthandoff: 02/24/2017

---
# <a name="calloc"></a>calloc
Ordnet ein Array im Arbeitsspeicher mit Elementen an, die auf 0 initialisiert sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
void *calloc(   
   size_t num,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `num`  
 Anzahl der Elemente.  
  
 `size`  
 Länge jedes Elements in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `calloc` gibt einen Zeiger auf den zugewiesenen Speicherplatz zurück. Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als `void` zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
## <a name="remarks"></a>Hinweise  
 Die `calloc`-Funktion reserviert Speicherplatz für ein Array von `num`-Elementen, die jeweils die Länge `size` Bytes haben. Jedes Element wird auf 0 initialisiert.  
  
 `calloc` setzt `errno` auf `ENOMEM`, wenn eine Speicherbelegung fehlschlägt oder wenn der benötigte Speicherplatz größer ist als `_HEAP_MAXREQ`. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `calloc` ruft `malloc` auf, um mithilfe der C++-Funktion [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) den neuen Handlermodus festzulegen. Der neue Handlermodus gibt an, ob `malloc` bei einem Fehler die neue Handlerroutine aufrufen soll, wie dies durch [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) festgelegt ist. Standardmäßig ruft `malloc` bei einem Speicherbelegungsfehler nicht die neue Handlerroutine auf. Sie können dieses Standardverhalten überschreiben, sodass, wenn `calloc` Speicher nicht belegen kann,`malloc` die neue Handlerroutine genauso aufruft wie der `new`-Operator, wenn dieser aus demselben Grund fehlschlägt. Um den Standardwert zu überschreiben, rufen Sie  
  
```  
_set_new_mode(1)  
```  
  
 rechtzeitig im Programm auf oder stellen eine Verknüpfung mit NEWMODE.OBJ her (siehe [Link Options (Linkoptionen)](../../c-runtime-library/link-options.md)).  
  
 Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, wird `calloc` in [_calloc_dbg](../../c-runtime-library/reference/calloc-dbg.md) aufgelöst. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
 `calloc` ist als `__declspec(noalias)` und `__declspec(restrict)` gekennzeichnet, das bedeutet, dass die Funktion globale Variablen definitiv nicht ändert und dass der zurückgegebene Zeiger keinen Alias hat. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`calloc`|\<stdlib.h> und \<malloc.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
Allocated 40 long integers  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)
