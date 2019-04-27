---
title: gets_s, _getws_s
ms.date: 11/04/2016
apiname:
- _getws_s
- gets_s
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
- _getws_s
- gets_s
helpviewer_keywords:
- getws_s function
- _getws_s function
- lines, getting
- streams, getting lines
- buffers, avoiding overruns
- buffer overruns
- buffers, buffer overruns
- gets_s function
- standard input, reading from
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
ms.openlocfilehash: f71fafceaf1974bc5ff736ff175a67cf6c924ee6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157655"
---
# <a name="getss-getwss"></a>gets_s, _getws_s

Ruft eine Zeile aus der **Stdin** Stream. Diese Versionen von [gets, _getws](../../c-runtime-library/gets-getws.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitserweiterungen im CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

## <a name="syntax"></a>Syntax

```C
char *gets_s(
   char *buffer,
   size_t sizeInCharacters
);
wchar_t *_getws_s(
   wchar_t *buffer,
   size_t sizeInCharacters
);
```

```cpp
template <size_t size>
char *gets_s( char (&buffer)[size] ); // C++ only

template <size_t size>
wchar_t *_getws_s( wchar_t (&buffer)[size] ); // C++ only
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für die Eingabezeichenfolge.

*sizeInCharacters*<br/>
Die Größe des Puffers.

## <a name="return-value"></a>Rückgabewert

Gibt *Puffer* bei erfolgreicher Ausführung. Ein **NULL**-Zeiger weist auf einen Fehler oder eine Dateiendebedingung hin. Verwenden Sie [ferror](ferror.md) oder [feof](feof.md) , um festzulegen, was aufgetreten ist.

## <a name="remarks"></a>Hinweise

Die **Gets_s** Funktion liest eine Zeile aus dem Standardeingabestream **Stdin** und speichert ihn in *Puffer*. Die Zeile enthält alle Zeichen einschließlich des ersten Zeilenumbruchzeichens ('\n'). **Gets_s** ersetzt dann das neue Zeilenumbruchzeichen mit einem Null-Zeichen ('\0'), ehe die Zeile zurückgegeben. Im Gegensatz dazu die **Fgets_s** das neue Zeilenumbruchzeichen beibehalten.

Wenn das erste gelesene Zeichen das EOF Zeichen ist, wird ein Null-Zeichen am Anfang gespeichert *Puffer* und **NULL** zurückgegeben wird.

**_getws_s** ist eine Breitzeichen-Version von **Gets_s**; das Argument und der Rückgabewert sind Breitzeichen Zeichenfolgen.

Wenn *Puffer* ist **NULL** oder *SizeInCharacters* ist kleiner als oder gleich 0 (null) oder wenn der Puffer zu klein für die Eingabezeile und der null-Terminator ist, rufen diese Funktionen ein Handler für ungültige Parameter wie beschrieben in [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **NULL** , und legen Sie Errno auf **ERANGE**.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_getts_s**|**gets_s**|**gets_s**|**_getws_s**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**gets_s**|\<stdio.h>|
|**_getws_s**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps für universelle Windows-Plattform (UWP) nicht unterstützt. Standardstreamhandles, die mit der Konsole verknüpft sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in UWP-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_gets_s.c
// This program retrieves a string from the stdin and
// prints the same string to the console.

#include <stdio.h>

int main( void )
{
   char line[21]; // room for 20 chars + '\0'
   gets_s( line, 20 );
   printf( "The line entered was: %s\n", line );
}
```

```Input
Hello there!
```

```Output
The line entered was: Hello there!
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
