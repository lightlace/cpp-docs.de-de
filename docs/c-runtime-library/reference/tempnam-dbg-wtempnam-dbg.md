---
title: _tempnam_dbg, _wtempnam_dbg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28b917ce2f50d9b766fd305f3320664d11e93da2
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg, _wtempnam_dbg

Funktionsversionen von [_tempnam _wtempnam, Tmpnam _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) , verwenden die Debugversion des **"malloc"**, **_malloc_dbg**.

## <a name="syntax"></a>Syntax

```C
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

### <a name="parameters"></a>Parameter

*dir*<br/>
Der im Dateinamen verwendete Pfad, wenn es keine TMP-Umgebungsvariable gibt oder wenn TMP kein gültiges Verzeichnis ist.

*prefix*<br/>
Die Zeichenfolge, die von zurückgegebenen Namen vorangestellt werden **_tempnam**.

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger zum Namen der Quelldatei, die Belegung angefordert oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in die Belegung angefordert wurde, oder **NULL**.

## <a name="return-value"></a>Rückgabewert

Jede Funktion gibt einen Zeiger auf den Namen generiert oder **NULL** , wenn ein Fehler auftritt. Fehler kann auftreten, wenn ein Ungültiger Verzeichnisname angegeben, in der TMP-Umgebungsvariable und die *Dir* Parameter.

> [!NOTE]
> **Kostenlose** (oder **Free_dbg**) muss aufgerufen werden, damit von belegte Zeiger **_tempnam_dbg** und **_wtempnam_dbg**.

## <a name="remarks"></a>Hinweise

Die **_tempnam_dbg** und **_wtempnam_dbg** -Funktionen sind identisch mit **_tempnam** und **_wtempnam** mit dem Unterschied, dass, wenn **_DEBUG** wird definiert, verwenden Sie diese Funktionen die Debugversion des **"malloc"** und **_malloc_dbg**, um Speicher zuzuordnen **NULL** ist als erster Parameter übergeben. Weitere Informationen finden Sie unter [_malloc_dbg](malloc-dbg.md).

In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen können Sie definieren Sie das Flag **_CRTDBG_MAP_ALLOC**. Wenn **_CRTDBG_MAP_ALLOC** definiert ist, werden Aufrufe von **_tempnam** und **_wtempnam** neu zu **_tempnam_dbg** und **_ Wtempnam_dbg**nahezu mit der *BlockType* festgelegt **_NORMAL_BLOCK**. Daher, Sie müssen nicht auf diese Funktionen explizit aufrufen, wenn Sie die Heapblöcke als markieren möchten **_CLIENT_BLOCK**. Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttempnam_dbg**|**_tempnam_dbg**|**_tempnam_dbg**|**_wtempnam_dbg**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_tempnam_dbg**, **_wtempnam_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
