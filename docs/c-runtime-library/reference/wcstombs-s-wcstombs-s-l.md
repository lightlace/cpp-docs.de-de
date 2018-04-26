---
title: wcstombs_s, _wcstombs_s_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wcstombs_s_l
- wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
dev_langs:
- C++
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d392e2a970627cd59d4cb96ae354c3b15406731e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="wcstombss-wcstombssl"></a>wcstombs_s, _wcstombs_s_l

Konvertiert eine Breitzeichensequenz in eine entsprechende Multibyte-Zeichensequenz. Dies ist eine sicherere Version von [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md), wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t wcstombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count
);

errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);

template <size_t size>
errno_t wcstombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only

template <size_t size>
errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*pReturnValue*<br/>
Die Anzahl von konvertierten Zeichen.

*mbstr*<br/>
Die Pufferadresse für die resultierende konvertierte Multibyte-Zeichenfolge.

*sizeInBytes*<br/>
Die Größe in Bytes, der die *Mbstr* Puffer.

*wcstr*<br/>
Zeigt auf die zu konvertierende Breitzeichenfolge.

*count*<br/>
Die maximale Anzahl von Bytes zum Speichern in der *Mbstr* Puffer, nicht einschließlich des abschließenden Null-Zeichens, oder [_TRUNCATE](../../c-runtime-library/truncate.md).

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, Fehlercode bei Fehler.

|Fehlerbedingung|Rückgabewert und **Errno**|
|---------------------|------------------------------|
|*Mbstr* ist **NULL** und *SizeInBytes* > 0|**EINVAL**|
|*Wcstr* ist **NULL**|**EINVAL**|
|Der Zielpuffer ist zu klein, um die konvertierte Zeichenfolge enthalten (es sei denn, *Anzahl* ist **_TRUNCATE**; finden Sie unter "Hinweise" weiter unten)|**ERANGE**|

Wenn eine dieser Bedingungen auftritt, wird die Ausnahme für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion einen Fehlercode zurück und legt **Errno** wie in der Tabelle ersichtlich.

## <a name="remarks"></a>Hinweise

Die **Wcstombs_s** -Funktion konvertiert eine Zeichenfolge mit Breitzeichen verweist *Wcstr* in multibyte-Zeichen im Puffer, die durch gespeicherte *Mbstr*. Die Konvertierung wird für jedes Zeichen fortgesetzt, bis eine der folgenden Bedingungen eintritt:

- Ein Breitzeichen NULL wird erkannt.

- Ein Breitzeichen, das nicht konvertiert werden kann, wird erkannt.

- Die Anzahl der Bytes, die in gespeicherten der *Mbstr* Puffer ist gleich *Anzahl*.

Die Zielzeichenfolge endet immer mit NULL, selbst bei einem Fehler.

Wenn *Anzahl* der spezielle Wert [_TRUNCATE](../../c-runtime-library/truncate.md), klicken Sie dann **Wcstombs_s** konvertiert größtmöglicher Teil der Zeichenfolge wie in den Zielpuffer passt, während weiterhin Platz für ein NULL-Wert bleibt Abschlusszeichen. Wenn die Zeichenfolge abgeschnitten wird, ist der Rückgabewert **STRUNCATE**, und die Konvertierung wird als erfolgreich betrachtet.

Wenn **Wcstombs_s** die Quellzeichenfolge erfolgreich konvertiert er setzt die Größe in Bytes der konvertierten Zeichenfolge, einschließlich der null-Terminator in  *&#42;pReturnValue* (bereitgestellte  *pReturnValue* nicht **NULL**). Dies tritt auf, auch wenn die *Mbstr* Argument ist **NULL** und bietet eine Möglichkeit, die erforderliche Puffergröße bestimmen. Beachten Sie, dass bei *Mbstr* ist **NULL**, *Anzahl* wird ignoriert.

Wenn **Wcstombs_s** findet ein Breitzeichen, es kann nicht in einem multibyte-Zeichen konvertiert,-Zielpuffer 0 in  *&#42;pReturnValue*, Zielpuffers auf eine leere Zeichenfolge festgelegt wird, wird dadurch **Errno**  auf **EILSEQ**, und gibt **EILSEQ**.

Wenn die Sequenzen auf verweist *Wcstr* und *Mbstr* überlappen, ist das Verhalten des **Wcstombs_s** ist nicht definiert.

> [!IMPORTANT]
> Sicherstellen, dass *Wcstr* und *Mbstr* nicht überlappen und dass *Anzahl* die Anzahl der Breitzeichen, die zu konvertierende korrekt widerspiegelt.

**Wcstombs_s** verwendet das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten; **_wcstombs_s_l** ist identisch mit **Wcstombs** identisch, jedoch das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**wcstombs_s**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Programm veranschaulicht das Verhalten von der **Wcstombs_s** Funktion.

```C
// crt_wcstombs_s.c
// This example converts a wide character
// string to a multibyte character string.
#include <stdio.h>
#include <stdlib.h>
#include <assert.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t   i;
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t*pWCBuffer = L"Hello, world.";

    printf( "Convert wide-character string:\n" );

    // Conversion
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,
               pWCBuffer, (size_t)BUFFER_SIZE );

    // Output
    printf("   Characters converted: %u\n", i);
    printf("    Multibyte character: %s\n\n",
     pMBBuffer );

    // Free multibyte character buffer
    if (pMBBuffer)
    {
    free(pMBBuffer);
    }
}
```

```Output
Convert wide-character string:
   Characters converted: 14
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)<br/>
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
