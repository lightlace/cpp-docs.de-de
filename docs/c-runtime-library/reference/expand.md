---
title: _expand | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _expand
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
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: b82bcf0de4f17a718389ef358a11a88e9bd999c1
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="expand"></a>_expand
Ändert die Größe eines Speicherblocks.  
  
## <a name="syntax"></a>Syntax  
  
```  
void *_expand(   
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `memblock`  
 Zeiger zum vorherigen belegten Speicherblock.  
  
 `size`  
 Neue Größe in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `_expand` gibt einen leeren Zeiger auf den neu belegten Speicherblock zurück. `_expand` kann, im Gegensatz zu `realloc`, einen Block nicht verschieben, um dessen Größe zu ändern. Daher entspricht der `memblock`-Parameter auf `_expand` dem Rückgabewert, wenn genug Speicher vorhanden ist, um den Block auszudehnen, ohne ihn zu verschieben.  
  
 `_expand` gibt `NULL` zurück, wenn ein Fehler während des Vorgangs auftritt. Wenn `_expand` z.B. verwendet wird, um einen Speicherblock zu verkleinern, könnte eine Beschädigung im kleinen Blockheap oder ein ungültiger Blockzeiger festgestellt und `NULL` zurückgegeben werden.  
  
 Wenn nicht genügend Speicher vorhanden ist, um den Block auf die angegebene Größe auszudehnen, ohne ihn zu verschieben, gibt die Funktion `NULL` zurück. `_expand` gibt einen Block zurück, der auf eine kleinere Größe als angegeben ausgedehnt wurde. Wenn ein Fehler auftritt, gibt `errno` die Art des Fehlers an. Weitere Informationen zu `errno` finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Verwenden Sie `_msize`, um die neue Größe des Elements zu überprüfen. Um einen Zeiger auf einen anderen Typ als `void` zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
## <a name="remarks"></a>Hinweise  
 Die `_expand`-Funktion ändert die Größe eines zuvor belegten Speicherblocks, indem versucht wird, den Block ohne Verschieben seiner Position im Heap zu erweitern oder zu verkleinern. Der Parameter `memblock` zeigt auf den Anfang des Blocks. Der Parameter `size` gibt die neue Größe des Blocks in Bytes an. Der Inhalt des Blocks bleibt bis zum Minimum von neuer und alter Größe unverändert. `memblock` sollte kein Block sein, der freigegeben wurde.  
  
> [!NOTE]
>  Auf 64-Bit-Plattformen verkleinert `_expand` den Block möglicherweise nicht, wenn die neue Größe kleiner ist als die aktuelle Größe. Besonders wenn der Block kleiner als 16K war und daher im niedrigen Fragmentierungs-Heap belegt war, ändert `_expand` den Block nicht und gibt `memblock` zurück.  
  
 Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, wird `_expand` in [_expand_dbg](../../c-runtime-library/reference/expand-dbg.md) aufgelöst. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [The CRT Debug Heap (CRT-Debugheap)](/visualstudio/debugger/crt-debug-heap-details).  
  
 Diese Funktion überprüft ihre Parameter. Wenn `memblock` ein NULL-Zeiger ist, ruft diese Funktion einen Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL`zurück. Wenn `size` größer als `_HEAP_MAXREQ` ist, wird `errno` auf `ENOMEM` festgelegt, und die Funktion gibt `NULL` zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_expand`|\<malloc.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_expand.c  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char *bufchar;  
   printf( "Allocate a 512 element buffer\n" );  
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )  
      exit( 1 );  
   printf( "Allocated %d bytes at %Fp\n",   
         _msize( bufchar ), (void *)bufchar );  
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )  
      printf( "Can't expand" );  
   else  
      printf( "Expanded block to %d bytes at %Fp\n",   
            _msize( bufchar ), (void *)bufchar );  
   // Free memory   
   free( bufchar );  
   exit( 0 );  
}  
```  
  
```Output  
Allocate a 512 element buffer  
Allocated 512 bytes at 002C12BC  
Expanded block to 1024 bytes at 002C12BC  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_msize](../../c-runtime-library/reference/msize.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)
