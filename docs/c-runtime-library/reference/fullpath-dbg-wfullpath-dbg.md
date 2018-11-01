---
title: _fullpath_dbg, _wfullpath_dbg
ms.date: 11/04/2016
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
helpviewer_keywords:
- _fullpath_dbg function
- relative file paths
- absolute paths
- fullpath_dbg function
- _wfullpath_dbg function
- wfullpath_dbg function
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
ms.openlocfilehash: b84c5b77d0a9bfb298d4c597e372cd39a92441f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488009"
---
# <a name="fullpathdbg-wfullpathdbg"></a>_fullpath_dbg, _wfullpath_dbg

Versionen von [_fullpath, _wfullpath](fullpath-wfullpath.md) , verwenden die Debugversion des **Malloc** um Speicher zu belegen.

## <a name="syntax"></a>Syntax

```C
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

### <a name="parameters"></a>Parameter

*absPath*<br/>
Zeiger auf einen Puffer, der den absoluten oder vollständigen Pfadnamen enthält oder **NULL**.

*relPath*<br/>
Relativer Pfadname.

*MaxLength*<br/>
Maximale Länge des Puffers Namen absoluten Pfad (*AbsPath*). Diese Länge ist, in Bytes für **_fullpath** jedoch in Breitzeichen (**"wchar_t"**) für **_wfullpath**.

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die Belegung angefordert oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in denen die Belegung angefordert wurde, oder **NULL**.

## <a name="return-value"></a>Rückgabewert

Jede Funktion gibt einen Zeiger auf einen Puffer, enthält des absolute Pfadname (*AbsPath*). Wenn ein Fehler auftritt (z. B., wenn der Wert übergeben *RelPath* enthält einen Laufwerkbuchstaben an, die ist ungültig oder wurde nicht gefunden, oder wenn die Länge der erstellte absolute Pfadname (*AbsPath*) ist größer als *MaxLength*) die Funktion gibt **NULL**.

## <a name="remarks"></a>Hinweise

Die **_fullpath_dbg** und **_wfullpath_dbg** -Funktionen sind identisch mit **_fullpath** und **_wfullpath** mit dem Unterschied, dass wenn **_DEBUG** wird definiert, verwenden Sie diese Funktionen die Debugversion von **Malloc**, **_malloc_dbg**, um Arbeitsspeicher zu belegen, wenn **NULL** übergeben wird als ersten Parameter. Informationen zu den Debugfunktionen von **_malloc_dbg**, finden Sie unter [_malloc_dbg](malloc-dbg.md).

In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen können Sie definieren die **_CRTDBG_MAP_ALLOC** Flag. Wenn **_CRTDBG_MAP_ALLOC** definiert ist, werden Aufrufe von **_fullpath** und **_wfullpath** neu zu **_fullpath_dbg** und **_wfullpath_dbg**, mit der *BlockType* festgelegt **_NORMAL_BLOCK**. Also, Sie müssen nicht dieser Funktionen explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als markieren **_CLIENT_BLOCK**. Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath_dbg**|**_fullpath_dbg**|**_fullpath_dbg**|**_wfullpath_dbg**|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_fullpath_dbg**|\<crtdbg.h>|
|**_wfullpath_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
