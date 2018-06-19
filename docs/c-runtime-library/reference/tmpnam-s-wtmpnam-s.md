---
title: tmpnam_s, _wtmpnam_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- tmpnam_s
- _wtmpnam_s
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
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
dev_langs:
- C++
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8c6298c7b66c8967a4e5e23a37c3614edcddf3d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415525"
---
# <a name="tmpnams-wtmpnams"></a>tmpnam_s, _wtmpnam_s

Generiert Namen, die Sie verwenden können, um temporäre Dateien zu erstellen. Dabei handelt es sich um Versionen von [tmpnam und _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) mit den unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschriebenen Erweiterungen.

## <a name="syntax"></a>Syntax

```C
errno_t tmpnam_s(
   char * str,
   size_t sizeInChars
);
errno_t _wtmpnam_s(
   wchar_t *str,
   size_t sizeInChars
);
template <size_t size>
errno_t tmpnam_s(
   char (&str)[size]
); // C++ only
template <size_t size>
errno_t _wtmpnam_s(
   wchar_t (&str)[size]
); // C++ only
```

### <a name="parameters"></a>Parameter

*str*<br/>
Zeiger, der den generierten Namen enthalten wird.

*sizeInChars*<br/>
Größe des Puffers in Zeichen.

## <a name="return-value"></a>Rückgabewert

Beide Funktionen geben bei Erfolg 0 zurück und bei einem Fehler eine Fehlernummer zurück.

### <a name="error-conditions"></a>Fehlerbedingungen

|||||
|-|-|-|-|
|*str*|*sizeInChars*|**Rückgabewert**|**Inhalt der***str* |
|**NULL**|alle|**EINVAL**|nicht geändert|
|Nicht **NULL** (verweist auf gültige Speicher)|zu kurz|**ERANGE**|nicht geändert|

Wenn *str* ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL** inventurüberprüfung **EINVAL**.

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen gibt den Namen einer Datei zurück, die derzeit nicht vorhanden ist. **Tmpnam_s** gibt einen Namen in das aktuelle Arbeitsverzeichnis eindeutig. Wenn einem Dateinamen ohne Pfadinformationen ein umgekehrter Schrägstrich vorangestellt ist, wie z.B. \fname21, weist dies darauf hin, dass der Name für das aktuelle Arbeitsverzeichnis gültig ist.

Für **Tmpnam_s**, können Sie im generierten Dateinamen speichern *str*. Die maximale Länge einer Zeichenfolge zurückgegebenes **Tmpnam_s** ist **L_tmpnam_s**, die in STDIO definiert. H. Wenn *str* ist **NULL**, klicken Sie dann **Tmpnam_s** bewirkt, dass das Ergebnis in einer statischen internen Puffer. Alle nachfolgenden Aufrufe zerstören deshalb diesen Wert. Der Name von generierten **Tmpnam_s** besteht aus einem Programm generierten Dateinamen und nach dem ersten Aufruf von **Tmpnam_s**, einer Erweiterung von aufeinander folgenden Nummern Basis 32 (.1-.1vvvvvu When **TMP _MAX_S** in STDIO. H **INT_MAX**).

**Tmpnam_s** behandelt Multibyte-Zeichenfolgen Zeichenfolgenargumente, wobei Multibyte-Zeichensequenzen entsprechend der OEM-Codepage erkannt automatisch abgerufen, von dem Betriebssystem. **_wtmpnam_s** ist eine Breitzeichen-Version von **Tmpnam_s**; der Wert Argument- und Rückgabetypen der **_wtmpnam_s** sind Zeichenfolgen mit Breitzeichen. **_wtmpnam_s** und **Tmpnam_s** Verhalten sich identisch, außer dass **_wtmpnam_s** verarbeitet keine Multibyte-Zeichenfolgen.

Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads (Sichere Vorlagenüberladungen)](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam_s**|**tmpnam_s**|**tmpnam_s**|**_wtmpnam_s**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**tmpnam_s**|\<stdio.h>|
|**_wtmpnam_s**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_tmpnam_s.c
// This program uses tmpnam_s to create a unique filename in the
// current working directory.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char name1[L_tmpnam_s];
   errno_t err;
   int i;

   for (i = 0; i < 15; i++)
   {
      err = tmpnam_s( name1, L_tmpnam_s );
      if (err)
      {
         printf("Error occurred creating unique filename.\n");
         exit(1);
      }
      else
      {
         printf( "%s is safe to use as a temporary file.\n", name1 );
      }
   }
}
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
