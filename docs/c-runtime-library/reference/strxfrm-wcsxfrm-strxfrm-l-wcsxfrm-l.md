---
title: strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strxfrm
- _tcsxfrm
- wcsxfrm
dev_langs:
- C++
helpviewer_keywords:
- strxfrm_l function
- _tcsxfrm function
- _strxfrm_l function
- strxfrm function
- wcsxfrm_l function
- wcsxfrm function
- string comparison [C++], transforming strings
- tcsxfrm function
- strings [C++], comparing locale
- _wcsxfrm_l function
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96f459c8360969146f8cf76a48c9141000066745
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214292"
---
# <a name="strxfrm-wcsxfrm-strxfrml-wcsxfrml"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l

Transformieren einer Zeichenfolge auf der Grundlage von gebietsschemaspezifischen Informationen

## <a name="syntax"></a>Syntax

```C
size_t strxfrm(
   char *strDest,
   const char *strSource,
   size_t count
);
size_t wcsxfrm(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count
);
size_t _strxfrm_l(
   char *strDest,
   const char *strSource,
   size_t count,
   _locale_t locale
);
size_t wcsxfrm_l(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*strDest*<br/>
Zielzeichenfolge.

*strSource*<br/>
Quellzeichenfolge.

*count*<br/>
Maximale Anzahl von Zeichen in platzieren *StrDest*.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt die Länge der transformierten Zeichenfolge ohne Berücksichtigung des beendenden Null-Zeichens zurück. Der zurückgegebene Wert ist größer als oder gleich *Anzahl*, wird der Inhalt der *StrDest* ist unvorhersehbar. Bei einem Fehler legt jede Funktion **Errno** und gibt **INT_MAX**. Für ein ungültiges Zeichen **Errno** nastaven NA hodnotu **EILSEQ**.

## <a name="remarks"></a>Hinweise

Die **Strxfrm** -Funktion transformiert die Zeichenfolge verweist *StrSource* in eine neue sortierte Form, die in gespeicherten *StrDest*. Nicht mehr als *Anzahl* Zeichen, einschließlich des Null-Zeichens, transformiert und in die Ergebniszeichenfolge eingefügt werden. Die Transformation erfolgt mithilfe des Gebietsschemas **LC_COLLATE** -kategorieeinstellung. Weitere Informationen zu **LC_COLLATE**, finden Sie unter [Setlocale](setlocale-wsetlocale.md). **Strxfrm** verwendet das aktuelle Gebietsschema für ihr vom Gebietsschema abhängige Verhalten; **_strxfrm_l** ist identisch mit dem Unterschied, dass Sie verwendet jedoch den Gebietsschemaparameter anstelle des aktuellen Gebietsschemas übergeben. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Nach der Transformation, die einen Aufruf von **Strcmp** mit den beiden transformierten Zeichenfolgen Ergebnisse, die identisch mit denen eines Aufrufs von sehen **Strcoll** auf die ursprünglichen beiden Zeichenfolgen angewendet. Wie bei **Strcoll** und **Stricoll**, **Strxfrm** behandelt automatisch die Multibyte-Zeichenfolgen entsprechend.

**Wcsxfrm** ist eine Breitzeichen-Version von **Strxfrm**; die Zeichenfolgenargumente von **Wcsxfrm** sind Breitzeichen-Zeiger. Für **Wcsxfrm**nach Transformationen von Zeichenfolgen, die einen Aufruf von **Wcscmp** mit den beiden transformierten Zeichenfolgen Ergebnisse, die identisch mit denen eines Aufrufs von sehen **Wcscoll** angewendet werden, um die ursprünglichen beiden Zeichenfolgen. **Wcsxfrm** und **Strxfrm** Verhalten sich andernfalls identisch. **Wcsxfrm** verwendet das aktuelle Gebietsschema für ihr vom Gebietsschema abhängige Verhalten; **_wcsxfrm_l** verwendet das Gebietsschema anstelle des aktuellen Gebietsschemas übergeben.

Diese Funktionen überprüfen ihre Parameter. Wenn *StrSource* ist ein null-Zeiger oder *StrDest* ist eine **NULL** Zeiger (es sei denn, die Anzahl Null ist), oder wenn *Anzahl* ist größer als **INT_MAX**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** zu **EINVAL** und zurückgeben **INT_MAX**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

Im Gebietsschema „C“ ist die Reihenfolge der Zeichen im Zeichensatz (ASCII-Zeichensatz) die gleiche wie die lexikografische Reihenfolge von Zeichen. In anderen Gebietsschemata kann die Reihenfolge der Zeichen im Zeichensatz jedoch von der lexikografischen Reihenfolge der Zeichen abweichen. In bestimmten europäischen Gebietsschemata beispielsweise steht im Zeichensatz das Zeichen „a“ (Wert 0x61) vor dem Zeichen „&\#x00E4;“ (Wert 0xE4), das Zeichen „ä“ steht lexikografisch gesehen jedoch vor dem Zeichen „a“.

In Gebietsschemas, die für die der Zeichensatz und die lexikografische Zeichenreihenfolge unterschiedlich sind, verwenden Sie **Strxfrm** für die ursprünglichen Zeichenfolgen und dann **Strcmp** für die resultierenden Zeichenfolgen, um eine lexikografische Zeichenfolge zu erzeugen. Vergleich anhand des aktuellen Gebietsschemas **LC_COLLATE** -kategorieeinstellung. Verwenden Sie daher zum Vergleichen von zwei Zeichenfolgen lexikografisch im obigen Gebietsschema **Strxfrm** auf die ursprünglichen Zeichenfolgen und dann **Strcmp** für die resultierenden Zeichenfolgen. Alternativ können Sie **Strcoll** statt **Strcmp** für die ursprünglichen Zeichenfolgen.

**Strxfrm** ist im Grunde genommen ein Wrapper um [LCMapString](/windows/desktop/api/winnls/nf-winnls-lcmapstringa) mit **LCMAP_SORTKEY**.

Der Wert des folgenden Ausdrucks ist die Größe des Arrays zum Speichern der **Strxfrm** Transformation der Quellzeichenfolge:

`1 + strxfrm( NULL, string, 0 )`

Im Gebietsschema "C" nur **Strxfrm** entspricht der folgenden:

```C
strncpy( _string1, _string2, _count );
return( strlen( _string1 ) );
```

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strxfrm**|\<string.h>|
|**wcsxfrm**|\<string.h> oder \<wchar.h>|
|**_strxfrm_l**|\<string.h>|
|**_wcsxfrm_l**|\<string.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
