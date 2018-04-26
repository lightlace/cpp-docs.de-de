---
title: ferror | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ferror
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ferror
dev_langs:
- C++
helpviewer_keywords:
- ferror function
- streams, testing for errors
- errors [C++], testing for stream
ms.assetid: 528a34bc-f2aa-4c3f-b89a-5b148e6864f7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3baec1f3f8775b422aa9e0e5da3a6eb3e738e74b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="ferror"></a>ferror

Testet auf einen Fehler in einem Stream

## <a name="syntax"></a>Syntax

```C
int ferror(
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Wenn kein Fehler aufgetreten ist, auf *Stream*, **Ferror** gibt 0 zurück. Andernfalls gibt es einen Wert ungleich 0 (null) zurück. Wenn der Stream ist **NULL**, **Ferror** wird den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt 0 zurück.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Ferror** Routine (sowohl als Funktion und als Makro implementiert) für eine Lesen oder Schreiben auf die zugeordnete Datei Fehler testet *Stream*. Wenn ein Fehler aufgetreten ist, der Fehlerindikator für Streams bleibt festgelegt, bis der Stream geschlossen ist oder zurückgesetzt wird, oder bis **Clearerr** gegenüber diesem aufgerufen wird.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**ferror**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Sehen Sie sich das Beispiel für [feof](feof.md) an.

## <a name="see-also"></a>Siehe auch

[Fehlerbehandlung](../../c-runtime-library/error-handling-crt.md)<br/>
[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
