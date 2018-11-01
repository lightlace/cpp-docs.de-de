---
title: _getdcwd_dbg, _wgetdcwd_dbg
ms.date: 11/04/2016
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
helpviewer_keywords:
- working directory
- _getdcwd_dbg function
- wgetdcwd_dbg function
- current working directory
- getdcwd_dbg function
- _wgetdcwd_dbg function
- directories [C++], current working
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
ms.openlocfilehash: 700cfe732dc390ca59a976694403bb3d91af5980
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547173"
---
# <a name="getdcwddbg-wgetdcwddbg"></a>_getdcwd_dbg, _wgetdcwd_dbg

Debugversionen der Funktionen [_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md) (nur während des Debuggens verfügbar).

## <a name="syntax"></a>Syntax

```C
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

### <a name="parameters"></a>Parameter

*Laufwerk*<br/>
Name des Laufwerks.

*buffer*<br/>
Speicherort für den Pfad.

*maxlen*<br/>
Maximale Länge des Pfads in Zeichen: **Char** für **_getdcwd_dbg** und **"wchar_t"** für **_wgetdcwd_dbg**.

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die die Belegung angefordert hat oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in denen die Belegung angefordert wurde, oder **NULL**.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf *Puffer*. Ein **NULL** Rückgabewert gibt einen Fehler an und **Errno** entweder auf festgelegt ist **ENOMEM**, gibt an, dass nicht genügend Arbeitsspeicher zuordnen *Maxlen* Bytes (Wenn eine **NULL** Argument erhält als *Puffer*), oder **ERANGE**, der angibt, dass der Pfad länger als *Maxlen*  Zeichen. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_getdcwd_dbg** und **_wgetdcwd_dbg** -Funktionen sind identisch mit **_getdcwd** und **_wgetdcwd** mit dem Unterschied, dass wenn **_DEBUG** wird definiert, verwenden Sie diese Funktionen die Debugversion von **Malloc** und **_malloc_dbg** um Speicher zu belegen, wenn **NULL** übergeben wird als die *Puffer* Parameter. Weitere Informationen finden Sie unter [_malloc_dbg](malloc-dbg.md).

In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen können Sie definieren die **_CRTDBG_MAP_ALLOC** Flag. Wenn **_CRTDBG_MAP_ALLOC** definiert ist, werden Aufrufe von **_getdcwd** und **_wgetdcwd** neu zu **_getdcwd_dbg** und **_ Wgetdcwd_dbg**, mit der *BlockType* festgelegt **_NORMAL_BLOCK**. Also, Sie müssen nicht dieser Funktionen explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als markieren **_CLIENT_BLOCK**. Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd_dbg**|**_getdcwd_dbg**|**_getdcwd_dbg**|**_wgetdcwd_dbg**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_getdcwd_dbg**|\<crtdbg.h>|
|**_wgetdcwd_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[Verzeichnissteuerung](../../c-runtime-library/directory-control.md)<br/>
[Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
