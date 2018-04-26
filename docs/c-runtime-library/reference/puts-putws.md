---
title: puts, _putws | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _putws
- puts
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
- _putts
- _putws
- puts
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], writing
- _putts function
- standard output, writing to
- putws function
- puts function
- putts function
- _putws function
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a823106478e575f9b2d65bc4e739236098da5124
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="puts-putws"></a>puts, _putws

Schreibt eine Zeichenfolge in **stdout**.

## <a name="syntax"></a>Syntax

```C
int puts(
   const char *str
);
int _putws(
   const wchar_t *str
);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ausgabezeichenfolge.

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg einen nicht negativen Wert zurück. Wenn **versetzt** fehlschlägt, wird **EOF**; Wenn **_putws** fehlschlägt, wird **WEOF**. Wenn *str* ist ein null-Zeiger, der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen die Funktionen **Errno** auf **EINVAL** inventurüberprüfung **EOF** oder **WEOF**.

Weitere Informationen über diese und andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (_doserrno, errno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **versetzt** -Funktion schreibt *str* in den Standardausgabestream **"stdout"**, ersetzen die Zeichenfolge abschließende Null-Zeichen ('\0') mit einem neue Zeilenvorschubzeichen ("\n") in der der Ausgabestream.

**_putws** ist die Breitzeichen-Version des **versetzt**; die zwei Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **setzt** derzeit die Ausgabe in eine Unicode-Stream unterstützt keine.

**_putwch** Unicode-Zeichen mit der aktuellen Einstellung des KONSOLENGEBIETSSCHEMAS.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_putts**|**puts**|**puts**|**_putws**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**puts**|\<stdio.h>|
|**_putws**|\<stdio.h>|

Die Konsole wird in apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstream Handles, die mit der Konsole verknüpften sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in uwp-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_puts.c
// This program uses puts to write a string to stdout.

#include <stdio.h>

int main( void )
{
   puts( "Hello world from puts!" );
}
```

### <a name="output"></a>Ausgabe

```Output
Hello world from puts!
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
