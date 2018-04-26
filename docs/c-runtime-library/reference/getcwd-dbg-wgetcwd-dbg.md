---
title: _getcwd_dbg, _wgetcwd_dbg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 59bf95e03891f787ec8271d35d4b922d8641dda2
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="getcwddbg-wgetcwddbg"></a>_getcwd_dbg, _wgetcwd_dbg

Debugversionen der Funktionen [_getcwd, _wgetcwd](getcwd-wgetcwd.md) (nur während des Debuggens verfügbar).

## <a name="syntax"></a>Syntax

```C
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

### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für den Pfad.

*maxlen*<br/>
Maximale Länge des Pfads in Zeichen: **Char** für **_getcwd_dbg** und **Wchar_t** für **_wgetcwd_dbg**.

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die die Belegung angefordert oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in die Belegung angefordert wurde, oder **NULL**.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf *Puffer*. Ein **NULL** -Rückgabewert zeigt einen Fehler und **Errno** entweder auf festgelegt ist **ENOMEM**, gibt an, dass nicht genügend Arbeitsspeicher zuweisen *Maxlen* Bytes (Wenn eine **NULL** Argument erhält als *Puffer*), oder auf **ERANGE**, der angibt, dass der Pfad länger als *Maxlen*  Zeichen.

Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_getcwd_dbg** und **_wgetcwd_dbg** -Funktionen sind identisch mit **_getcwd** und **_wgetcwd** mit dem Unterschied, dass, wenn **_ DEBUGGEN** wird definiert, verwenden Sie diese Funktionen die Debugversion des **"malloc"** und **_malloc_dbg** Arbeitsspeicher belegt werden, wenn **NULL** übergeben wird, als der erste Parameter. Weitere Informationen finden Sie unter [_malloc_dbg](malloc-dbg.md).

In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen können Sie definieren die **_CRTDBG_MAP_ALLOC** Flag. Wenn **_CRTDBG_MAP_ALLOC** definiert ist, werden Aufrufe von **_getcwd** und **_wgetcwd** neu zu **_getcwd_dbg** und **_ Wgetcwd_dbg**nahezu mit der *BlockType* festgelegt **_NORMAL_BLOCK**. Daher, Sie müssen nicht auf diese Funktionen explizit aufrufen, wenn Sie die Heapblöcke als markieren möchten **_CLIENT_BLOCK**. Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

## <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd_dbg**|**_getcwd_dbg**|**_getcwd_dbg**|**_wgetcwd_dbg**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_getcwd_dbg**|\<crtdbg.h>|
|**_wgetcwd_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[Verzeichnissteuerung](../../c-runtime-library/directory-control.md)<br/>
[Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
