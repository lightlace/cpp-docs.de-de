---
title: vscanf_s, vwscanf_s
ms.date: 11/04/2016
apiname:
- vscanf_s
- vwscanf_s
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
- _vtscanf_s
- vscanf_s
- vwscanf_s
ms.assetid: 23a1c383-5b01-4887-93ce-534a1e38ed93
ms.openlocfilehash: 90100a5fbc03371a11f437acc12562d9ccf957f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519469"
---
# <a name="vscanfs-vwscanfs"></a>vscanf_s, vwscanf_s

Liest formatierte Daten aus dem Standardeingabestream. Diese Versionen von [vscanf, vwscanf](vscanf-vwscanf.md) enthalten Sicherheitserweiterungen, wie unter [Security Features in the CRT (Sicherheitserweiterungen in der CRT)](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
int vscanf_s(
   const char *format,
   va_list arglist
);
int vwscanf_s(
   const wchar_t *format,
   va_list arglist
);
```

### <a name="parameters"></a>Parameter

*format*<br/>
Formatsteuerzeichenfolge.

*arglist*<br/>
Variablenargumentenliste.

## <a name="return-value"></a>Rückgabewert

Gibt die Anzahl von Feldern zurück, die erfolgreich konvertiert und zugewiesen wurden; der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden. Der Rückgabewert ist **EOF** ein Fehler, oder wenn das EOF Zeichen oder das Ende der Zeichenfolge Zeichen, beim ersten Versuch erreicht ist, ein Zeichen zu lesen. Wenn *Format* ist eine **NULL** -Zeiger ist, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Vscanf_s** und **Vwscanf_s** zurückgeben **EOF** und **Errno** zu **EINVAL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (errno, _doserrno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Vscanf_s** -Funktion liest Daten aus dem Standardeingabestream **Stdin** und schreibt die Daten in die Speicherorte, die von erhalten die *Arglist* Argumentliste. Jedes Argument in der Liste muss ein Zeiger auf eine Variable eines Typs, der einem Typspezifizierer in entspricht *Format*. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.

**Vwscanf_s** ist eine Breitzeichen-Version von **Vscanf_s**; die *Format* Argument **Vwscanf_s** ist eine Breitzeichen-Zeichenfolge. **Vwscanf_s** und **Vscanf_s** Verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **Vscanf_s** unterstützt keine Eingabe aus einem unicodestream.

Im Gegensatz zu **Vscanf** und **Vwscanf**, **Vscanf_s** und **Vwscanf_s** benötigen Sie die Größe des Puffers angegeben werden, für alle des Typs Eingabeparameter **c**, **C**, **s**, **S**, oder, die in eingeschlossen sind **[]**. Die Puffergröße in Zeichen wird als zusätzlicher Parameter direkt nach dem Zeiger auf den Puffer oder die Variable übergeben. Die Größe des Puffers in Zeichen für eine **"wchar_t"** Zeichenfolge ist nicht identisch mit der Größe in Byte.

Die Puffergröße enthält das abschließende NULL-Zeichen. Sie können ein Feld für die Breitenangabe verwenden, um sicherzustellen, dass das eingelesene Token in den Puffer passt. Wenn kein Feld für die Breiteangabe verwendet wird und das eingelesen Token zu groß für den Puffer ist, wird nichts in diesen Puffer geschrieben.

> [!NOTE]
> Die *Größe* Parameter ist vom Typ **ohne Vorzeichen**, nicht **"size_t"**.

Weitere Informationen finden Sie unter [scanf Width Specification (scanf-Breitenangabe)](../../c-runtime-library/scanf-width-specification.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtscanf_s**|**vscanf_s**|**vscanf_s**|**vwscanf_s**|

Weitere Informationen finden Sie unter [Format Specification Fields: scanf and wscanf Functions (Formatspezifikationsfelder: Funktionen scanf und wscanf)](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**vscanf_s**|\<stdio.h>|
|**wscanf_s**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps für universelle Windows-Plattform (UWP) nicht unterstützt. Standardstreamhandles, die mit der Konsole verknüpft sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in UWP-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_vscanf_s.c
// compile with: /W3
// This program uses the vscanf_s and vwscanf_s functions
// to read formatted input.

#include <stdio.h>
#include <stdarg.h>
#include <stdlib.h>

int call_vscanf_s(char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vscanf_s(format, arglist);
    va_end(arglist);
    return result;
}

int call_vwscanf_s(wchar_t *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vwscanf_s(format, arglist);
    va_end(arglist);
    return result;
}

int main( void )
{
    int   i, result;
    float fp;
    char  c, s[81];
    wchar_t wc, ws[81];
    result = call_vscanf_s("%d %f %c %C %s %S", &i, &fp, &c, 1,
                           &wc, 1, s, _countof(s), ws, _countof(ws) );
    printf( "The number of fields input is %d\n", result );
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);
    result = call_vwscanf_s(L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,
                            &wc, 1, s, _countof(s), ws, _countof(ws) );
    wprintf( L"The number of fields input is %d\n", result );
    wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);
}
```

Wenn diesem Programm die Eingabe aus dem Beispiel übergeben wird, erzeugt es Folgendes:

```Input
71 98.6 h z Byte characters
36 92.3 y n Wide characters
```

```Output
The number of fields input is 6
The contents are: 71 98.599998 h z Byte characters
The number of fields input is 6
The contents are: 36 92.300003 y n Wide characters
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[vscanf, vwscanf](vscanf-vwscanf.md)<br/>
