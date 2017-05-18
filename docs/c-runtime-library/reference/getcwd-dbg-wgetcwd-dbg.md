---
title: _getcwd_dbg, _wgetcwd_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wgetcwd_dbg
- _getcwd_dbg
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd_dbg
- _wgetcwd_dbg
- getcwd_dbg
- wgetcwd_dbg
dev_langs:
- C++
helpviewer_keywords:
- wgetcwd_dbg function
- working directory
- _getcwd_dbg function
- getcwd_dbg function
- current working directory
- _wgetcwd_dbg function
- directories [C++], current working
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
caps.latest.revision: 15
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 9814916e32878a1e1a11f534fce64aeaf2f6a57e
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="getcwddbg-wgetcwddbg"></a>_getcwd_dbg, _wgetcwd_dbg
Debugversionen der Funktionen [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md) (nur während des Debuggens verfügbar).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_getcwd_dbg(   
   char *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wgetcwd_dbg(   
   wchar_t *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `buffer`  
 Speicherort für den Pfad.  
  
 `maxlen`  
 Maximale Länge des Pfads in Zeichen: `char` für `_getcwd_dbg` und `wchar_t` für `_wgetcwd_dbg`.  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger auf den Namen der Quelldatei, die die Belegung angefordert hat, oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder `NULL`.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf `buffer`zurück. Ein `NULL` -Rückgabewert zeigt einen Fehler an, und `errno` wird entweder auf `ENOMEM`festgelegt, um anzugeben, dass nicht genügend Arbeitsspeicher zum Zuordnen von `maxlen` Bytes vorhanden ist (wenn ein `NULL` -Argument als `buffer`angegeben wird), oder auf `ERANGE`, um anzugeben, dass der Pfad länger als `maxlen` Zeichen ist.  
  
 Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_getcwd_dbg` und `_wgetcwd_dbg` -Funktionen sind identisch mit `_getcwd` und `_wgetcwd` mit dem Unterschied, dass, wenn `_DEBUG` wird definiert, verwenden Sie diese Funktionen die Debugversion des `malloc` und `_malloc_dbg` Arbeitsspeicher belegt werden, wenn `NULL` als erster Parameter übergeben wird. Weitere Informationen finden Sie unter [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen können Sie das `_CRTDBG_MAP_ALLOC`-Flag definieren. Wenn `_CRTDBG_MAP_ALLOC` definiert ist, werden Aufrufe von `_getcwd` und `_wgetcwd` zu `_getcwd_dbg` bzw. `_wgetcwd_dbg` neu zugeordnet, wobei `blockType` auf `_NORMAL_BLOCK` festgelegt wird. Daher müssen Sie diese Funktionen nicht explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als `_CLIENT_BLOCK` markieren. Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetcwd_dbg`|`_getcwd_dbg`|`_getcwd_dbg`|`_wgetcwd_dbg`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_getcwd_dbg`|\<crtdbg.h>|  
|`_wgetcwd_dbg`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)
