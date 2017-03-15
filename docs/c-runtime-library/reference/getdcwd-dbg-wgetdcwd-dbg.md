---
title: _getdcwd_dbg, _wgetdcwd_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getdcwd_dbg
- _wgetdcwd_dbg
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
- _getdcwd_dbg
- getdcwd_dbg
- _wgetdcwd_dbg
- wgetdcwd_dbg
dev_langs:
- C++
helpviewer_keywords:
- working directory
- _getdcwd_dbg function
- wgetdcwd_dbg function
- current working directory
- getdcwd_dbg function
- _wgetdcwd_dbg function
- directories [C++], current working
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
caps.latest.revision: 14
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
ms.openlocfilehash: 4c4f63690395398698624fd75d1450ef4bcb7287
ms.lasthandoff: 02/24/2017

---
# <a name="getdcwddbg-wgetdcwddbg"></a>_getdcwd_dbg, _wgetdcwd_dbg
Debugversionen der Funktionen [_getdcwd, _wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md) (nur während des Debuggens verfügbar).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_getdcwd_dbg(  
   int drive,  
   char *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wgetdcwd_dbg(  
   int drive,  
   wchar_t *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `drive`  
 Name des Laufwerks.  
  
 `buffer`  
 Speicherort für den Pfad.  
  
 `maxlen`  
 Maximale Länge des Pfads in Zeichen: `char` für `_getdcwd_dbg` und `wchar_t` für `_wgetdcwd_dbg`.  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger auf den Namen der Quelldatei, die die Belegung angefordert hat, oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder `NULL`.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf `buffer`zurück. Ein `NULL` -Rückgabewert zeigt einen Fehler an, und `errno` wird entweder auf `ENOMEM`festgelegt, um anzugeben, dass nicht genügend Arbeitsspeicher zum Zuordnen von `maxlen` Bytes vorhanden ist (wenn ein `NULL` -Argument als `buffer`angegeben wird), oder auf `ERANGE`, um anzugeben, dass der Pfad länger als `maxlen` Zeichen ist. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_getdcwd_dbg`- und `_wgetdcwd_dbg`-Funktionen sind identisch mit `_getdcwd` und `_wgetdcwd`, außer dass bei Definition von `_DEBUG` diese Funktionen die Debugversion von `malloc` und `_malloc_dbg` verwenden, um Speicher zuzuordnen, wenn `NULL` als `buffer`-Parameter übergeben wird. Weitere Informationen finden Sie unter [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen können Sie das `_CRTDBG_MAP_ALLOC`-Flag definieren. Wenn `_CRTDBG_MAP_ALLOC` definiert ist, werden Aufrufe von `_getdcwd` und `_wgetdcwd` zu `_getdcwd_dbg` bzw. `_wgetdcwd_dbg` neu zugeordnet, wobei `blockType` auf `_NORMAL_BLOCK` festgelegt wird. Daher müssen Sie diese Funktionen nicht explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als `_CLIENT_BLOCK` markieren. Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetdcwd_dbg`|`_getdcwd_dbg`|`_getdcwd_dbg`|`_wgetdcwd_dbg`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_getdcwd_dbg`|\<crtdbg.h>|  
|`_wgetdcwd_dbg`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 <xref:System.Environment.CurrentDirectory%2A?displayProperty=fullName>  
  
## <a name="see-also"></a>Siehe auch  
 [_getdcwd, _wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)
