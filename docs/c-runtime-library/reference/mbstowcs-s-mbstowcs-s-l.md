---
title: mbstowcs_s, _mbstowcs_s_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbstowcs_s_l
- mbstowcs_s
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
- _mbstowcs_s_l
- mbstowcs_s
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3457195b07335345476153038d7ab38606607a2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217358"
---
# <a name="mbstowcss-mbstowcssl"></a>mbstowcs_s, _mbstowcs_s_l

Konvertiert eine Multibyte-Zeichensequenz in eine entsprechende Breitzeichensequenz. Versionen von [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) mit Sicherheitsverbesserungen wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count
);
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*pReturnValue*<br/>
Die Anzahl von konvertierten Zeichen.

*wcstr*<br/>
Pufferadresse zum Speichern der resultierenden konvertierten Breitzeichenfolge.

*sizeInWords*<br/>
Die Größe der *Wcstr* Puffers in Worten.

*mbstr*<br/>
Adresse einer Multibyte-Zeichensequenz.

*count*<br/>
Die maximale Anzahl von Breitzeichen, das Speichern in der *Wcstr* Puffer, ohne das abschließende Nullzeichen oder [_TRUNCATE](../../c-runtime-library/truncate.md).

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, Fehlercode bei Fehler.

|Fehlerbedingung|Rückgabewert und **Errno**|
|---------------------|------------------------------|
|*Wcstr* ist **NULL** und *SizeInWords* > 0|**EINVAL**|
|*Mbstr* ist **NULL**|**EINVAL**|
|Der Zielpuffer ist zu klein, um die konvertierte Zeichenfolge enthalten (es sei denn, *Anzahl* ist **_TRUNCATE**; Siehe Hinweise unten)|**ERANGE**|
|*Wcstr* nicht **NULL** und *SizeInWords* == 0|**EINVAL**|

Wenn eine dieser Bedingungen auftritt, wird die Ausnahme für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion einen Fehlercode zurück und legt **Errno** wie in der Tabelle angegeben.

## <a name="remarks"></a>Hinweise

Die **Mbstowcs_s** -Funktion konvertiert eine Zeichenfolge mit Multibytezeichen verweist *Mbstr* in Breitzeichen, die in den Puffer, die auf gespeicherten *Wcstr*. Die Konvertierung wird für jedes Zeichen fortgesetzt, bis eine der folgenden Bedingungen eintritt:

- Ein Multibyte-Nullzeichen wird erkannt.

- Ein ungültiges Multibytezeichen wird erkannt.

- Die Anzahl der gespeicherten Breitzeichen die *Wcstr* Puffer ist gleich *Anzahl*.

Die Zielzeichenfolge endet immer mit NULL, selbst bei einem Fehler.

Wenn *Anzahl* der spezielle Wert [_TRUNCATE](../../c-runtime-library/truncate.md), klicken Sie dann **Mbstowcs_s** konvertiert Anteil der Zeichenfolge wie in den Zielpuffer passt, und weiterhin Platz für ein NULL-Wert Abschlusszeichen.

Wenn **Mbstowcs_s** die Quellzeichenfolge erfolgreich konvertiert wird die Größe in Breitzeichen der konvertierten Zeichenfolge ist, einschließlich der null-Terminator in  *&#42;pReturnValue* (bereitgestellt von *pReturnValue* nicht **NULL**). Dies tritt auf, auch wenn die *Wcstr* Argument **NULL** und bietet eine Möglichkeit, um die Größe des erforderlichen Puffers zu bestimmen. Beachten Sie, dass bei *Wcstr* ist **NULL**, *Anzahl* ignoriert, und *SizeInWords* muss 0 sein.

Wenn **Mbstowcs_s** ein ungültiges Multibytezeichen erkennt, schreibt es 0 in  *&#42;pReturnValue*, festgelegt, der Zielpuffer auf eine leere Zeichenfolge **Errno** zu  **EILSEQ**, und gibt **EILSEQ**.

Wenn die Sequenzen, zeigt *Mbstr* und *Wcstr* überlappen, ist das Verhalten der **Mbstowcs_s** ist nicht definiert.

> [!IMPORTANT]
> Sicherstellen, dass *Wcstr* und *Mbstr* nicht überlappen und dass *Anzahl* die Anzahl zu konvertierendermultibytezeichen korrekt darstellt.

**Mbstowcs_s** verwendet das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten; **_mbstowcs_s_l** ist identisch, außer dass sie das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**mbstowcs_s**|\<stdlib.h>|
|**_mbstowcs_s_l**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
