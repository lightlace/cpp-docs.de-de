---
title: _fullpath_dbg, _wfullpath_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfullpath_dbg
- _fullpath_dbg
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
- wfullpath_dbg
- _wfullpath_dbg
- _fullpath_dbg
- fullpath_dbg
dev_langs:
- C++
helpviewer_keywords:
- _fullpath_dbg function
- relative file paths
- absolute paths
- fullpath_dbg function
- _wfullpath_dbg function
- wfullpath_dbg function
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
caps.latest.revision: 16
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 13dea0e3f4fdaef74d4806373376d5c84904ce8f
ms.lasthandoff: 02/24/2017

---
# <a name="fullpathdbg-wfullpathdbg"></a>_fullpath_dbg, _wfullpath_dbg
Versionen von [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md), die die Debugversion von `malloc` zur Speicherbelegung verwenden  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_fullpath_dbg(   
   char *absPath,  
   const char *relPath,  
   size_t maxLength,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wfullpath_dbg(   
   wchar_t *absPath,  
   const wchar_t *relPath,  
   size_t maxLength,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `absPath`  
 Zeiger auf einen Puffer, der den absoluten oder vollständigen Pfadnamen enthält, oder `NULL`.  
  
 `relPath`  
 Relativer Pfadname.  
  
 `maxLength`  
 Maximale Länge des Puffers des absoluten Pfadnamens (`absPath`). Die Länge wird für `_fullpath` in Bytes ausgedrückt, aber für `wchar_t` in Breitzeichen (`_wfullpath`).  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger zum Namen der Quelldatei, die die Zuordnung angefordert hat, oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder `NULL`.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede Funktion gibt einen Zeiger auf einen Puffer zurück, der den absoluten Pfadnamen (`absPath`) enthält. Wenn ein Fehler auftritt (z. B, wenn der in `relPath` übergebene Wert einen Laufwerksbuchstaben enthält, der nicht gültig ist oder nicht gefunden werden kann oder wenn der erstellte absolute Pfadname (`absPath`) länger ist als `maxLength`), gibt die Funktion `NULL` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktionen `_fullpath_dbg` und `_wfullpath_dbg` sind mit `_fullpath` und `_wfullpath` nahezu identisch, allerdings verwenden diese Funktionen, wenn _`DEBUG` definiert ist, die Debugversion von `malloc`, `_malloc_dbg`, um Speicher zu belegen, wenn NULL als erster Parameter übergeben wird. Weitere Informationen zu den Debugfunktionen von `_malloc_dbg` finden Sie unter [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen können Sie das Flag `_CRTDBG_MAP_ALLOC` definieren. Wenn `_CRTDBG_MAP_ALLOC` definiert ist, werden Aufrufe von `_fullpath` und `_wfullpath` zu `_fullpath_dbg` bzw. `_wfullpath_dbg` neu zugeordnet, wobei `blockType` auf `_NORMAL_BLOCK` festgelegt wird. Daher müssen Sie diese Funktionen nicht explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als `_CLIENT_BLOCK` markieren. Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfullpath_dbg`|`_fullpath_dbg`|`_fullpath_dbg`|`_wfullpath_dbg`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_fullpath_dbg`|\<crtdbg.h>|  
|`_wfullpath_dbg`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 <xref:System.IO.File.Create%2A>  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)
