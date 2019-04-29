---
title: sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l
ms.date: 11/04/2016
apiname:
- _sscanf_s_l
- sscanf_s
- _swscanf_s_l
- swscanf_s
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _stscanf_s
- sscanf_s
- swscanf_s
- _swscanf_s_l
- _stscanf_s_l
- _sscanf_s_l
helpviewer_keywords:
- stscanf_s_l function
- stscanf_s function
- swscanf_s function
- swscanf_s_l function
- sscanf_s_l function
- _stscanf_s_l function
- strings [C++], reading data from
- sscanf_s function
- _swscanf_s_l function
- _stscanf_s function
- reading data, strings
- strings [C++], reading
- _sscanf_s_l function
ms.assetid: 956e65c8-00a5-43e8-a2f2-0f547ac9e56c
ms.openlocfilehash: 07911b7254e74c28310669a697c7492b69567b7f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354796"
---
# <a name="sscanfs-sscanfsl-swscanfs-swscanfsl"></a>sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l

Liest formatierte Daten aus einer Zeichenfolge. Diese Versionen von [sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md) enthalten Sicherheitsverbesserungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
int sscanf_s(
   const char *buffer,
   const char *format [,
   argument ] ...
);
int _sscanf_s_l(
   const char *buffer,
   const char *format,
   locale_t locale [,
   argument ] ...
);
int swscanf_s(
   const wchar_t *buffer,
   const wchar_t *format [,
   argument ] ...
);
int _swscanf_s_l(
   const wchar_t *buffer,
   const wchar_t *format,
   locale_t locale [,
   argument ] ...
);
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Gespeicherte Daten

*format*<br/>
Formatsteuerzeichenfolge. Weitere Informationen finden Sie unter [Format Specification Fields: scanf and wscanf Functions (Formatspezifikationsfelder: Funktionen scanf und wscanf)](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*argument*<br/>
Optionale Argumente

*locale*<br/>
Das zu verwendende Gebietsschema

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt die Anzahl der Felder zurück, die erfolgreich konvertiert und zugewiesen wurden; der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden. Der Rückgabewert ist **EOF** für einen Fehler oder am Ende der Zeichenfolge vor der ersten Konvertierung erreicht wird.

Wenn *Puffer* oder *Format* ist eine **NULL** -Zeiger ist, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen-1 zurück und legen Sie **Errno** zu **EINVAL**

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (errno, _doserrno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Sscanf_s** -Funktion liest Daten aus *Puffer* an der Position, die von jeder Instanz erhält *Argument*. Die Argumente nach der Formatzeichenfolge geben Zeiger zu den Variablen, die einen Typ aufweisen, der einem Typspezifizierer in entspricht *Format*. Im Gegensatz zu den weniger sicheren Version [Sscanf](sscanf-sscanf-l-swscanf-swscanf-l.md), ein puffergrößenparameter ist erforderlich, bei der Verwendung der typfeldzeichen **c**, **C**, **s**, **S**, oder, die in eingeschlossen sind **[]**. Nach jedem Pufferparameter, der dies erfordert, muss die Puffergröße in Zeichen als zusätzlicher Parameter angegeben werden. Beim Einlesen einer Zeichenfolge wird beispielsweise die Puffergröße für diese Zeichenfolge wie folgt übergeben:

```C
wchar_t ws[10];
swscanf_s(in_str, L"%9s", ws, (unsigned)_countof(ws)); // buffer size is 10, width specification is 9
```

Die Puffergröße enthält das abschließende NULL-Zeichen. Ein Feld für die Breitenangabe muss verwendet werden, um sicherzustellen, dass das eingelesene Token in den Puffer passt. Wenn kein Feld für die Breiteangabe verwendet wird und das eingelesen Token zu groß für den Puffer ist, wird nichts in diesen Puffer geschrieben.

Im Fall von Zeichen wird ein einzelnes Zeichen wie folgt gelesen:

```C
wchar_t wc;
swscanf_s(in_str, L"%c", &wc, 1);
```

In diesem Beispiel wird ein einzelnes Zeichen aus der Eingabezeichenfolge gelesen und dann in einem Breitzeichenpuffer gespeichert. Wenn mehrere Zeichen für Zeichenfolgen gelesen werden, die nicht mit NULL abschließen, werden ganze Zahlen ohne Vorzeichen für die Breitenangabe und die Puffergröße verwendet.

```C
char c[4];
sscanf_s(input, "%4c", &c, (unsigned)_countof(c)); // not null terminated
```

Weitere Informationen finden Sie unter [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) und [scanf-Typenfeldzeichen](../../c-runtime-library/scanf-type-field-characters.md).

> [!NOTE]
> Size-Parameter ist vom Typ **ohne Vorzeichen**, nicht **"size_t"**. Wenn für 64-Bit-Ziele kompiliert wird, verwenden Sie eine statische Umwandlung konvertieren **_countof** oder **"sizeof"** Ergebnisse an die richtige Größe.

Die *Format* -Argument steuert die Interpretation der Eingabefelder und hat die gleiche form und Funktion wie der *Format* Argument für die **Scanf_s** Funktion. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.

**Swscanf_s** ist eine Breitzeichen-Version von **Sscanf_s**; die Argumente für **Swscanf_s** sind Breitzeichen Zeichenfolgen. **Sscanf_s** verarbeitet keine multibyte-Hexadezimalzeichen. **Swscanf_s** verarbeitet keine Unicode-voller Breite Hexadezimal- oder im "Kompatibilität der Zone" Zeichen. Andernfalls **Swscanf_s** und **Sscanf_s** Verhalten sich identisch.

Die Versionen dieser Funktionen, die **_l** -Suffix sind beinahe identisch, außer dass sie verwenden den Gebietsschemaparameter, der übergeben wird anstelle des aktuellen threadgebietsschemas.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stscanf_s**|**sscanf_s**|**sscanf_s**|**swscanf_s**|
|**_stscanf_s_l**|**_sscanf_s_l**|**_sscanf_s_l**|**_swscanf_s_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**sscanf_s**, **_sscanf_s_l**|\<stdio.h>|
|**swscanf_s**, **_swscanf_s_l**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_sscanf_s.c
// This program uses sscanf_s to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char  tokenstring[] = "15 12 14...";
   char  s[81];
   char  c;
   int   i;
   float fp;

   // Input various data from tokenstring:
   // max 80 character string plus null terminator
   sscanf_s( tokenstring, "%s", s, (unsigned)_countof(s) );
   sscanf_s( tokenstring, "%c", &c, (unsigned)sizeof(char) );
   sscanf_s( tokenstring, "%d", &i );
   sscanf_s( tokenstring, "%f", &fp );

   // Output the data read
   printf_s( "String    = %s\n", s );
   printf_s( "Character = %c\n", c );
   printf_s( "Integer:  = %d\n", i );
   printf_s( "Real:     = %f\n", fp );
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
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l](snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)<br/>
