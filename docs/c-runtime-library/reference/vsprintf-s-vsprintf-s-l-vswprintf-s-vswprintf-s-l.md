---
title: vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l
ms.date: 03/26/2019
apiname:
- _vswprintf_s_l
- vsprintf_s
- vswprintf_s
- _vsprintf_s_l
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
- vswprintf_s
- vsprintf_s
- _vstprintf_s
helpviewer_keywords:
- _vstprintf_s_l function
- vsprintf_s_l function
- _vstprintf_s function
- vswprintf_s function
- vstprintf_s function
- vstprintf_s_l function
- vswprintf_s_l function
- vsprintf_s function
- _vsprintf_s_l function
- formatted text [C++]
- _vswprintf_s_l function
ms.assetid: 60e90518-57f0-4f1b-b732-f62a69702833
ms.openlocfilehash: 469a823d0f033a2f140d78a65cb0e69a3ef16d5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383450"
---
# <a name="vsprintfs-vsprintfsl-vswprintfs-vswprintfsl"></a>vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l

Schreiben von formatierter Ausgabe mithilfe eines Zeigers, der auf eine Liste von Argumenten zeigt. Dies sind Versionen von [vsprintf, _vsprintf_l, vswprintf, _vswprintf_l, \__vswprintf_l](vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md) mit Sicherheitsverbesserungen, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
int vsprintf_s(
   char *buffer,
   size_t numberOfElements,
   const char *format,
   va_list argptr
);
int _vsprintf_s_l(
   char *buffer,
   size_t numberOfElements,
   const char *format,
   locale_t locale,
   va_list argptr
);
int vswprintf_s(
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *format,
   va_list argptr
);
int _vswprintf_s_l(
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int vsprintf_s(
   char (&buffer)[size],
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int vswprintf_s(
   wchar_t (&buffer)[size],
   const wchar_t *format,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für die Ausgabe.

*numberOfElements*<br/>
Größe des *Puffer* in Zeichen.

*format*<br/>
Formatangabe.

*argptr*<br/>
Zeiger zur Liste der Argumente.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**Vsprintf_s** und **Vswprintf_s** Zurückgeben der Anzahl der geschriebenen Zeichen nicht einschließlich des abschließenden Zeichens Null oder ein negativer Wert, wenn ein Ausgabefehler auftritt. Wenn *Puffer* oder *Format* ein null-Zeiger ist, wenn *NumberOfElements* NULL ist, oder wenn Formatzeichenfolge ungültige Formatierung enthält Zeichen, die Handler für ungültige Parameter wird aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktionen-1 zurück und legen Sie **Errno** zu **EINVAL**.

Weitere Informationen über diese und andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (_doserrno, errno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste und formatiert und schreibt die angegebenen Daten in den Speicher verweist *Puffer*.

**Vswprintf_s** entspricht dem ISO-C-Standard für **Vswprintf**, erfordert, dass den zweiten Parameter, *Anzahl*, des Typs **"size_t"**.

Diese Funktionen unterscheiden sich von den nicht sicheren Versionen nur darin, dass die sicheren Versionen Positionsparameter unterstützen. Weitere Informationen finden Sie unter [printf-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).

Die Versionen dieser Funktionen mit den **_l** -Suffix sind beinahe identisch, außer dass sie den übergebenen Gebietsschemaparameter anstelle des aktuellen threadgebietsschemas Locale-Parameter verwenden.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vstprintf_s**|**vsprintf_s**|**vsprintf_s**|**vswprintf_s**|
|**_vstprintf_s_l**|**_vsprintf_s_l**|**_vsprintf_s_l**|**_vswprintf_s_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionale Header|
|-------------|---------------------|----------------------|
|**vsprintf_s**, **_vsprintf_s_l**|\<stdio.h> und \<stdarg.h>|\<varargs.h>*|
|**vswprintf_s**, **_vswprintf_s_l**|\<stdio.h> oder \<wchar.h> und \<stdarg.h>|\<varargs.h>*|

\* Benötigt für die Kompatibilität mit UNIX V.

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_vsprintf_s.c
// This program uses vsprintf_s to write to a buffer.
// The size of the buffer is determined by _vscprintf.

#include <stdlib.h>
#include <stdarg.h>

void test( char * format, ... )
{
   va_list args;
   int len;
   char * buffer;

   va_start( args, format );
   len = _vscprintf( format, args ) // _vscprintf doesn't count
                               + 1; // terminating '\0'
   buffer = malloc( len * sizeof(char) );
   vsprintf_s( buffer, len, format, args );
   puts( buffer );
   free( buffer );
   va_end( args );
}

int main( void )
{
   test( "%d %c %d", 123, '<', 456 );
   test( "%s", "This is a string" );
}
```

```Output
123 < 456
This is a string
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md)<br/>
[Syntax der Formatangabe: printf- und wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
