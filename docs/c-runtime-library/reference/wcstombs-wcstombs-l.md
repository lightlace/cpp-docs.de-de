---
title: wcstombs, _wcstombs_l
ms.date: 11/04/2016
apiname:
- wcstombs
- _wcstombs_l
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wcstombs
- _wcstombs_l
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
ms.openlocfilehash: d102cd74061faeb0c41823e6cf5c9a8ef335294f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188583"
---
# <a name="wcstombs-wcstombsl"></a>wcstombs, _wcstombs_l

Konvertiert eine Breitzeichensequenz in eine entsprechende Multibyte-Zeichensequenz. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md).

## <a name="syntax"></a>Syntax

```C
size_t wcstombs(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count
);
size_t _wcstombs_l(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
size_t wcstombs(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only
template <size_t size>
size_t _wcstombs_l(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*mbstr*<br/>
Die Adresse einer Multibyte-Zeichensequenz.

*wcstr*<br/>
Die Adresse einer Breitzeichensequenz.

*count*<br/>
Die maximale Anzahl von Bytes, die in der Multibyte-Ausgabezeichenfolge gespeichert werden können.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Wenn **Wcstombs** erfolgreich konvertiert die multibyte-Zeichenfolge, die Anzahl der Bytes, die in der multibyte-Ausgabezeichenfolge, ohne das abschließende Nullzeichen, (sofern vorhanden) geschrieben wird. Wenn die *Mbstr* Argument **NULL**, **Wcstombs** gibt die erforderliche Größe der Zielzeichenfolge in Bytes zurück. Wenn **Wcstombs** findet ein Breitzeichen ist, die in einem multibyte-Zeichen konvertiert werden kann 1, die in den Typ umgewandelt wird **"size_t"** und **Errno** zu **EILSEQ** .

## <a name="remarks"></a>Hinweise

Die **Wcstombs** -Funktion konvertiert die Zeichenfolge mit Breitzeichen verweist *Wcstr* auf die entsprechenden Multibytezeichen und speichert die Ergebnisse in die *Mbstr* Array. Die *Anzahl* Parameter gibt die maximale Anzahl von Bytes, die in der multibyte-Ausgabezeichenfolge gespeichert werden können (d. h. die Größe des *Mbstr*). Es ist allgemein nicht bekannt, wie viele Bytes bei der Konvertierung einer Breitzeichenfolge benötigt werden. Einige Breitzeichen benötigen nur ein Byte in der Ausgabezeichenfolge; andere erfordern zwei. Wenn zwei Bytes in der multibyte-Ausgabezeichenfolge für jedes Breitzeichen in der Eingabezeichenfolge (einschließlich der Null-Breitzeichen) vorhanden sind, ist das Ergebnis garantiert passend.

Wenn **Wcstombs** das Breitzeichen Null-Zeichen (L '\0') erkennt, entweder vor oder bei *Anzahl* auftritt, konvertiert es in eine 8-Bit-0 "und" beendet. Daher die Multibyte-Zeichenfolge an *Mbstr* ist Null-terminierte nur, wenn **Wcstombs** während der Konvertierung ein Breitzeichen Null findet. Wenn die Sequenzen, zeigt *Wcstr* und *Mbstr* überlappen, ist das Verhalten der **Wcstombs** ist nicht definiert.

Wenn die *Mbstr* Argument **NULL**, **Wcstombs** gibt die erforderliche Größe der Zielzeichenfolge in Bytes zurück.

**Wcstombs** überprüft die eigenen Parameter. Wenn *Wcstr* ist **NULL**, oder wenn *Anzahl* ist größer als **INT_MAX**, ruft diese Funktion den Handler für ungültige Parameter aus, wie in beschrieben. [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Die Funktion legt fest, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** zu **EINVAL** und gibt-1 zurück.

**Wcstombs** verwendet das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten; **_wcstombs_l** ist identisch, außer dass sie das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**wcstombs**|\<stdlib.h>|
|**_wcstombs_l**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Programm stellt das Verhalten der **Wcstombs** Funktion.

```C
// crt_wcstombs.c
// compile with: /W3
// This example demonstrates the use
// of wcstombs, which converts a string
// of wide characters to a string of
// multibyte characters.

#include <stdlib.h>
#include <stdio.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t  count;
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t *pWCBuffer = L"Hello, world.";

    printf("Convert wide-character string:\n" );

    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996
    // Note: wcstombs is deprecated; consider using wcstombs_s instead
    printf("   Characters converted: %u\n",
            count );
    printf("    Multibyte character: %s\n\n",
           pMBBuffer );

    free(pMBBuffer);
}
```

```Output
Convert wide-character string:
   Characters converted: 13
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
