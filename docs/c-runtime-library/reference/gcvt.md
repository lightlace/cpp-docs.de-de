---
title: _gcvt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _gcvt
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _gcvt
dev_langs:
- C++
helpviewer_keywords:
- _gcvt function
- _CVTBUFSIZE
- gcvt function
- floating-point functions, converting number to string
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 5761411e-c06b-409a-912f-810fe7f4bcb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d824d42a102aee68619d602044c39f398af177dc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32400979"
---
# <a name="gcvt"></a>_gcvt

Konvertiert einen Gleitkommawert in eine Zeichenfolge, die in einem Puffer gespeichert wird. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [_gcvt_s](gcvt-s.md).

## <a name="syntax"></a>Syntax

```C
char *_gcvt(
   double value,
   int digits,
   char *buffer
);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Zu konvertierender Wert.

*Ziffern*<br/>
Anzahl der gespeicherten signifikanten Ziffern.

*buffer*<br/>
Speicherort für das Ergebnis.

## <a name="return-value"></a>Rückgabewert

**_gcvt** gibt einen Zeiger auf die Zeichenfolge von Ziffern zurück.

## <a name="remarks"></a>Hinweise

Die **_gcvt** -Funktion konvertiert eine Gleitkommazahl *Wert* in eine Zeichenfolge (enthält Dezimaltrennzeichen und ein Byte möglichen Anmeldung) und speichert die Zeichenfolge in *Puffer*. Die *Puffer* muss groß genug für den konvertierten Wert plus ein abschließendes Nullzeichen, das automatisch angefügt wird. Wenn die Größe des Befehlspuffers von *Ziffern* + 1 verwendet wird, wird die Funktion überschreibt das Ende des Puffers. Dies geschieht, da die konvertierte Zeichenfolge ein Dezimaltrennzeichen enthält und Informationen über Zeichen und Exponenten enthalten kann. Es wird kein Überlauf bereitgestellt. **_gcvt** erzeugen versucht *Ziffern* Ziffern im Dezimalformat. Wenn es nicht möglich ist, erzeugt es *Ziffern* Ziffern im Exponentialformat. Bei der Konvertierung können Nachstellen von Nullen unterdrückt werden.

Ein *Puffer* Länge **_CVTBUFSIZE** reicht für alle Gleitkommawert Datenpunktwert.

Diese Funktion überprüft ihre Parameter. Wenn *Puffer* ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt **NULL**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_gcvt**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_gcvt.c
// compile with: /W3
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

int main( void )
{
   char buffer[_CVTBUFSIZE];
   double value = -1234567890.123;
   printf( "The following numbers were converted by _gcvt(value,12,buffer):\n" );
   _gcvt( value, 12, buffer ); // C4996
   // Note: _gcvt is deprecated; consider using _gcvt_s instead
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );

   printf( "\n" );
   value = -12.34567890123;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
}
```

```Output
The following numbers were converted by _gcvt(value,12,buffer):
buffer: '-1234567890.12' (14 chars)
buffer: '-12345678901.2' (14 chars)
buffer: '-123456789012' (13 chars)
buffer: '-1.23456789012e+012' (19 chars)

buffer: '-12.3456789012' (14 chars)
buffer: '-1.23456789012' (14 chars)
buffer: '-0.123456789012' (15 chars)
buffer: '-1.23456789012e-002' (19 chars)
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
