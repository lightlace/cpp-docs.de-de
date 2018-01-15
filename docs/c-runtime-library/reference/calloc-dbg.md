---
title: _calloc_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _calloc_dbg
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
apitype: DLLExport
f1_keywords:
- _calloc_dbg
- calloc_dbg
dev_langs: C++
helpviewer_keywords:
- _calloc_dbg function
- calloc_dbg function
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4295dd84e8066de0906a6fcd7b154c94875f7f5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="callocdbg"></a>_calloc_dbg
Belegt einige Speicherblöcke im Heap mit zusätzlichem Speicherplatz für einen Debugheader und Überschreibungspuffer (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
void *_calloc_dbg(   
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `num`  
 Angeforderte Anzahl von Speicherblöcken.  
  
 `size`  
 Angeforderte Größe eines Speicherblocks (Bytes).  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 Weitere Informationen zu den Zuordnungsblocktypen und ihrer Verwendung finden Sie unter [Types of Blocks on the Debug Heap (Blocktypen auf dem Debugheap)](/visualstudio/debugger/crt-debug-heap-details).  
  
 `filename`  
 Zeiger zum Namen der Quelldatei, der die Zuordnung angefordert hat, oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Zuordnung angefordert wurde, oder `NULL`.  
  
 Die Parameter `filename` und `linenumber` sind nur verfügbar, wenn `_calloc_dbg` explizit aufgerufen wurde oder die Präprozessorkonstante [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) definiert wurde.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei erfolgreichem Abschluss gibt diese Funktion entweder einen Zeiger an den Benutzerteil des zuletzt belegten Speicherblocks zurück, ruft die neue Handlerfunktion auf oder gibt `NULL` zurück. Eine vollständige Beschreibung des Rückgabeverhaltens finden Sie im Abschnitt "Hinweise". Weitere Informationen zur Verwendung der neuen Handlerfunktion finden Sie unter der [calloc](../../c-runtime-library/reference/calloc.md)-Funktion.  
  
## <a name="remarks"></a>Hinweise  
 `_calloc_dbg` ist eine Debugversion der [calloc](../../c-runtime-library/reference/calloc.md)-Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder `_calloc_dbg`-Aufruf zu einem `calloc`-Aufruf reduziert. `calloc` und `_calloc_dbg` belegen `num`-Speicherblöcke im Basisheap, jedoch bietet `_calloc_dbg` mehrere Debugfunktionen:  
  
-   Puffer auf beiden Seiten des Benutzerteils des Blocks zum Prüfen auf Speicherverluste.  
  
-   Blocktypparameter zum Nachverfolgen von bestimmten Belegungstypen.  
  
-   `filename`/`linenumber`-Informationen zum Ermitteln des Ursprungs von Belegungsanforderungen.  
  
 `_calloc_dbg` belegt jeden Speicherblock mit etwas mehr Speicherplatz als der angeforderten `size`. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Wenn der Block belegt wurde, wird der Benutzerteil des Blocks mit dem Wert "0xCD" gefüllt, und jeder der Überschreibungspuffer wird mit "0xFD" gefüllt.  
  
 `_calloc_dbg` legt `errno` auf `ENOMEM` fest, wenn eine Speicherbelegung fehlschlägt. `EINVAL` wird zurückgegeben, wenn der benötigte Speicherplatz (einschließlich des bereits erwähnten Mehraufwands) `_HEAP_MAXREQ` überschreitet. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_calloc_dbg`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_callocd.c  
/*  
 * This program uses _calloc_dbg to allocate space for  
 * 40 long integers. It initializes each element to zero.  
 */  
#include <stdio.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
        long *bufferN, *bufferC;  
  
        /*   
         * Call _calloc_dbg to include the filename and line number  
         * of our allocation request in the header and also so we can  
         * allocate CLIENT type blocks specifically  
         */  
        bufferN = (long *)_calloc_dbg( 40, sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );  
        bufferC = (long *)_calloc_dbg( 40, sizeof(long), _CLIENT_BLOCK, __FILE__, __LINE__ );  
        if( bufferN != NULL && bufferC != NULL )  
              printf( "Allocated memory successfully\n" );  
        else  
              printf( "Problem allocating memory\n" );  
  
        /*   
         * _free_dbg must be called to free CLIENT type blocks  
         */  
        free( bufferN );  
        _free_dbg( bufferC, _CLIENT_BLOCK );  
}  
```  
  
```Output  
Allocated memory successfully  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [_DEBUG](../../c-runtime-library/debug.md)