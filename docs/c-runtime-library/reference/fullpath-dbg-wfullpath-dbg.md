---
title: _fullpath_dbg, _wfullpath_dbg
ms.date: 11/04/2016
api_name:
- _wfullpath_dbg
- _fullpath_dbg
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 9271e26bcf4a78ff8d2e4fcf108f1e483c22c1d7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956312"
---
# <a name="_fullpath_dbg-_wfullpath_dbg"></a>_fullpath_dbg, _wfullpath_dbg

Versionen von [_fullpath, _wfullpath](fullpath-wfullpath.md) , die die Debugversion von **malloc** zum Zuordnen von Arbeitsspeicher verwenden.

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
Zeiger auf einen Puffer, der den absoluten oder vollständigen Pfadnamen enthält, oder **null**.

*relPath*<br/>
Relativer Pfadname.

*maxLength*<br/>
Maximale Länge des absoluten Pfadnamen Puffers (*abspath*). Diese Länge ist in Bytes für **_fullpath** , aber in breit Zeichen (**wchar_t**) für **_wfullpath**.

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die den Zuordnungs Vorgang angefordert hat, oder **null**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der der Zuordnungs Vorgang angefordert wurde, oder **null**.

## <a name="return-value"></a>Rückgabewert

Jede Funktion gibt einen Zeiger auf einen Puffer zurück, der den absoluten Pfadnamen (*abspath*) enthält. Wenn ein Fehler vorliegt (z. b. wenn der in *RelPath* übergebenen Wert einen Laufwerk Buchstaben enthält, der nicht gültig ist oder nicht gefunden werden kann, oder wenn die Länge des erstellten absoluten Pfadnamens (*abspath*) größer als *MaxLength*ist), gibt die Funktion zurück **. NULL**.

## <a name="remarks"></a>Hinweise

Die Funktionen **_fullpath_dbg** und **_wfullpath_dbg** sind mit **_fullpath** und **_wfullpath** identisch, außer dass bei Definition von **_DEBUG** die Debugversion von **malloc**, **_malloc_dbg**, , um Speicher zuzuweisen, wenn **null** als erster Parameter übergeben wird. Weitere Informationen zu den Debuggingfunktionen von **_malloc_dbg**finden Sie unter [_malloc_dbg](malloc-dbg.md).

In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen können Sie das **_CRTDBG_MAP_ALLOC** -Flag definieren. Wenn **_CRTDBG_MAP_ALLOC** definiert ist, werden Aufrufe von **_fullpath** und **_wfullpath** zu **_fullpath_dbg** bzw. **_wfullpath_dbg**neu zugeordnet, wobei *blockType* auf **_NORMAL_BLOCK**festgelegt ist. Daher müssen Sie diese Funktionen nicht explizit aufzurufen, es sei denn, Sie möchten die Heap Blöcke als **_CLIENT_BLOCK**markieren. Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

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
