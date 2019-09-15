---
title: vscanf, vwscanf
ms.date: 11/04/2016
api_name:
- vscanf
- vwscanf
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
- vscanf
- vwscanf
- _vtscanf
ms.assetid: d1df595b-11bc-4682-9441-a92616301e3b
ms.openlocfilehash: 86e6588f6309989317c4cee7ec398cfa809afe9b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945445"
---
# <a name="vscanf-vwscanf"></a>vscanf, vwscanf

Liest formatierte Daten aus dem Standardeingabestream. Sicherere Versionen dieser Funktion sind verfügbar. Informationen dazu finden Sie unter [vscanf_s, vwscanf_s](vscanf-s-vwscanf-s.md).

## <a name="syntax"></a>Syntax

```C
int vscanf(
   const char *format,
   va_list arglist
);
int vwscanf(
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

Gibt die Anzahl von Feldern zurück, die erfolgreich konvertiert und zugewiesen wurden. Der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden.

Wenn *Format* ein **null** -Zeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen **EOF** zurück und legen **errno** auf **EINVAL**fest.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (errno, _doserrno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **vscanf** -Funktion liest Daten aus dem Standardeingabestream **stdin** und schreibt die Daten in die Speicherorte, die von der *Arglist* -Argumentliste angegeben werden. Jedes Argument in der Liste muss ein Zeiger auf eine Variable eines Typs sein, der einem Typspezifizierer im- *Format*entspricht. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.

> [!IMPORTANT]
> Wenn Sie mit **vscanf** eine Zeichenfolge lesen, geben Sie immer eine Breite für das **% s** -Format an (z. b. **"% 32s"** anstelle von **"% s"** ); Andernfalls kann eine falsch formatierte Eingabe zu einem Pufferüberlauf führen. Alternativ können Sie auch [vscanf_s, vwscanf_s](vscanf-s-vwscanf-s.md) oder [fgets](fgets-fgetws.md) verwenden.

**vwscanf** ist eine breit Zeichen Version von **vscanf**. Das *Format* -Argument für **vwscanf** ist eine Zeichenfolge mit breit Zeichen. **vwscanf** und **vscanf** Verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **vscanf** unterstützt nicht die Eingabe aus einem Unicode-Stream.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtscanf**|**vscanf**|**vscanf**|**vwscanf**|

Weitere Informationen finden Sie unter [Format Specification Fields: scanf and wscanf Functions (Formatspezifikationsfelder: Funktionen scanf und wscanf)](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**vscanf**|\<stdio.h>|
|**vwscanf**|\<stdio.h> oder \<wchar.h>|

Die-Konsole wird in universelle Windows-Plattform-Apps (UWP) nicht unterstützt. Die Standarddaten Strom Handles, die der Konsole, **stdin**, **stdout**und **stderr**zugeordnet sind, müssen umgeleitet werden, bevor Sie von C-Lauf Zeitfunktionen in UWP-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_vscanf.c
// compile with: /W3
// This program uses the vscanf and vwscanf functions
// to read formatted input.

#include <stdio.h>
#include <stdarg.h>

int call_vscanf(char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vscanf(format, arglist);
    va_end(arglist);
    return result;
}

int call_vwscanf(wchar_t *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vwscanf(format, arglist);
    va_end(arglist);
    return result;
}

int main( void )
{
    int   i, result;
    float fp;
    char  c, s[81];
    wchar_t wc, ws[81];
    result = call_vscanf( "%d %f %c %C %80s %80S", &i, &fp, &c, &wc, s, ws );
    printf( "The number of fields input is %d\n", result );
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);
    result = call_vwscanf( L"%d %f %hc %lc %80S %80ls", &i, &fp, &c, &wc, s, ws );
    wprintf( L"The number of fields input is %d\n", result );
    wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);
}
```

```Output

      71 98.6 h z Byte characters
36 92.3 y n Wide charactersThe number of fields input is 6
The contents are: 71 98.599998 h z Byte characters
The number of fields input is 6
The contents are: 36 92.300003 y n Wide characters
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vscanf_s, vwscanf_s](vscanf-s-vwscanf-s.md)<br/>
