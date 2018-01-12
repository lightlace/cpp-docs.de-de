---
title: _tempnam_dbg, _wtempnam_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wtempnam_dbg
- _tempnam_dbg
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
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
dev_langs: C++
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 41c81b94187d2cd01adfa4a4ec469d78c6659897
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg, _wtempnam_dbg
Funktionsversionen von [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md), die die Debugversion von `malloc, _malloc_dbg` verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_tempnam_dbg(  
   const char *dir,  
   const char *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wtempnam_dbg(  
   const wchar_t *dir,  
   const wchar_t *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dir`  
 Der im Dateinamen verwendete Pfad, wenn es keine TMP-Umgebungsvariable gibt oder wenn TMP kein gültiges Verzeichnis ist.  
  
 `prefix`  
 Die Zeichenfolge, die den von `_tempnam` zurückgegebenen Namen vorangestellt wird.  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger auf den Namen der Quelldatei, die die Zuordnung angefordert hat, oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder `NULL`.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede Funktion gibt einen Zeiger auf den erzeugten Namen zurück oder `NULL`, falls ein Fehler vorliegt. Störungen können auftreten, wenn in der TMP-Umgebungsvariable und im `dir`-Parameter ein ungültiger Verzeichnisname angegeben wurde.  
  
> [!NOTE]
>  `free` (oder `free_dbg`) muss für von `_tempnam_dbg` und `_wtempnam_dbg` belegte Zeiger nicht aufgerufen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `_tempnam_dbg` und `_wtempnam_dbg` -Funktionen sind identisch mit `_tempnam` und `_wtempnam` mit dem Unterschied, dass, wenn `_DEBUG` wird definiert, verwenden Sie diese Funktionen die Debugversion des `malloc` und `_malloc_dbg`, um Speicher zuzuordnen `NULL` als erster Parameter übergeben wird. Weitere Informationen finden Sie unter [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen können Sie das `_CRTDBG_MAP_ALLOC`-Flag definieren. Wenn `_CRTDBG_MAP_ALLOC` definiert ist, werden Aufrufe von `_tempnam` und `_wtempnam` zu `_tempnam_dbg` bzw. `_wtempnam_dbg` neu zugeordnet, wobei `blockType` auf `_NORMAL_BLOCK` festgelegt wird. Daher müssen Sie diese Funktionen nicht explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als `_CLIENT_BLOCK` markieren. Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttempnam_dbg`|`_tempnam_dbg`|`_tempnam_dbg`|`_wtempnam_dbg`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_tempnam_dbg`, `_wtempnam_dbg`|\<crtdbg.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)