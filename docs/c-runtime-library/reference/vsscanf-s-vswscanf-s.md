---
title: vsscanf_s, vswscanf_s
ms.date: 11/04/2016
apiname:
- vswscanf_s
- vsscanf_s
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
- vsscanf_s
- vswscanf_s
- _vstscanf_s
ms.assetid: 7b732e68-c6f4-4579-8917-122f5a7876e1
ms.openlocfilehash: 3106e3533f5bb65334f8a4f3d38f55d886faef4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188711"
---
# <a name="vsscanfs-vswscanfs"></a>vsscanf_s, vswscanf_s

Liest formatierte Daten aus einer Zeichenfolge. Diese Versionen von [vsscanf, vswscanf](vsscanf-vswscanf.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
int vsscanf_s(
   const char *buffer,
   const char *format,
   va_list argptr
);
int vswscanf_s(
   const wchar_t *buffer,
   const wchar_t *format,
   va_list arglist
);
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Gespeicherte Daten

*format*<br/>
Formatsteuerzeichenfolge. Weitere Informationen finden Sie unter [Format Specification Fields: scanf and wscanf Functions (Formatspezifikationsfelder: Funktionen scanf und wscanf)](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*arglist*<br/>
Variablenargumentenliste.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt die Anzahl der Felder zurück, die erfolgreich konvertiert und zugewiesen wurden; der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden. Der Rückgabewert ist **EOF** für einen Fehler oder am Ende der Zeichenfolge vor der ersten Konvertierung erreicht wird.

Wenn *Puffer* oder *Format* ist eine **NULL** -Zeiger ist, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen-1 zurück und legen Sie **Errno** zu **EINVAL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (errno, _doserrno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Vsscanf_s** -Funktion liest Daten aus *Puffer* in die Speicherorte, die von jedem Argument im erhalten die *Arglist* Argumentliste. Die Argumente in der Argumentliste geben Zeiger zu den Variablen, die einen Typ aufweisen, der einem Typspezifizierer in entspricht *Format*. Im Gegensatz zu den weniger sicheren Version **Vsscanf**, ein puffergrößenparameter ist erforderlich, bei der Verwendung der typfeldzeichen **c**, **C**, **s**, **S**, oder legt ihn fest-Zeichenfolge-Steuerelement, die in eingeschlossen sind **[]**. Nach jedem Pufferparameter, der dies erfordert, muss die Puffergröße in Zeichen als zusätzlicher Parameter angegeben werden.

Die Puffergröße enthält das abschließende NULL-Zeichen. Ein Feld für die Breitenangabe muss verwendet werden, um sicherzustellen, dass das eingelesene Token in den Puffer passt. Wenn kein Feld für die Breiteangabe verwendet wird und das eingelesen Token zu groß für den Puffer ist, wird nichts in diesen Puffer geschrieben.

Weitere Informationen finden Sie unter [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) und [scanf-Typenfeldzeichen](../../c-runtime-library/scanf-type-field-characters.md).

> [!NOTE]
> Size-Parameter ist vom Typ **ohne Vorzeichen**, nicht **"size_t"**.

Die *Format* -Argument steuert die Interpretation der Eingabefelder und hat die gleiche form und Funktion wie der *Format* Argument für die **Scanf_s** Funktion. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.

**Vswscanf_s** ist eine Breitzeichen-Version von **Vsscanf_s**; die Argumente für **Vswscanf_s** sind Breitzeichen Zeichenfolgen. **Vsscanf_s** verarbeitet keine multibyte-Hexadezimalzeichen. **Vswscanf_s** verarbeitet keine Unicode-voller Breite Hexadezimal- oder im "Kompatibilität der Zone" Zeichen. Andernfalls **Vswscanf_s** und **Vsscanf_s** Verhalten sich identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vstscanf_s**|**vsscanf_s**|**vsscanf_s**|**vswscanf_s**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**vsscanf_s**|\<stdio.h>|
|**vswscanf_s**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_vsscanf_s.c
// compile with: /W3
// This program uses vsscanf_s to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdarg.h>
#include <stdlib.h>

int call_vsscanf_s(char *tokenstring, char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vsscanf_s(tokenstring, format, arglist);
    va_end(arglist);
    return result;
}

int main( void )
{
    char  tokenstring[] = "15 12 14...";
    char  s[81];
    char  c;
    int   i;
    float fp;

    // Input various data from tokenstring:
    // max 80 character string:
    call_vsscanf_s(tokenstring, "%80s", s, _countof(s));
    call_vsscanf_s(tokenstring, "%c", &c, sizeof(char));
    call_vsscanf_s(tokenstring, "%d", &i);
    call_vsscanf_s(tokenstring, "%f", &fp);

    // Output the data read
    printf("String    = %s\n", s);
    printf("Character = %c\n", c);
    printf("Integer:  = %d\n", i);
    printf("Real:     = %f\n", fp);
}
```

```Output
String    = 15
Character = 1
Integer:  = 15
Real:     = 15.000000
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vsscanf, vswscanf](vsscanf-vswscanf.md)<br/>
