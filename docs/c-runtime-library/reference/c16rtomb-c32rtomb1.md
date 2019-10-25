---
title: c16rtomb, c32rtomb
ms.date: 10/22/2019
api_name:
- c16rtomb
- c32rtomb
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
ms.openlocfilehash: 8f480d9b450b528275fea78ae878269fa6a4fa54
ms.sourcegitcommit: 0a5518fdb9d87fcc326a8507ac755936285fcb94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2019
ms.locfileid: "72811066"
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb

Konvertiert ein UTF-16-oder UTF-32-breit Zeichen in ein UTF-8-Multibytezeichen.

## <a name="syntax"></a>Syntax

```C
size_t c16rtomb(
    char *mbchar,
    char16_t wchar,
    mbstate_t *state
);
size_t c32rtomb(
    char *mbchar,
    char32_t wchar,
    mbstate_t *state
);
```

### <a name="parameters"></a>Parameter

*mbchar* -\
Zeiger auf ein Array zum Speichern des konvertierten UTF-8-multibytezeichens.

*WCHAR* -\
Ein zu konvertierendes Breitzeichen.

*Status* \
Ein Zeiger auf ein **mbstate_t** -Objekt.

## <a name="return-value"></a>Rückgabewert

Die Anzahl der im Array Objekt *mbchar*gespeicherten Bytes, einschließlich der Verschiebe Sequenzen. Wenn *WCHAR* kein gültiges breit Zeichen ist, wird der Wert (**size_t**) (-1) zurückgegeben, **errno** ist auf **EILSEQ**festgelegt, und der Wert des *Zustands* ist nicht angegeben.

## <a name="remarks"></a>Hinweise

Die **c16rtomb** -Funktion konvertiert das UTF-16-Le-Zeichen *WCHAR* in die entsprechende UTF-8-Multibytezeichen-schmale Zeichen Sequenz. Wenn *mbchar* kein NULL-Zeiger ist, speichert die Funktion die konvertierte Sequenz im Array Objekt, auf das von *mbchar*gezeigt wird. Bis zu **MB_CUR_MAX** Bytes werden in *mbchar*gespeichert, und *State* wird auf den resultierenden Multibytezeichen-UMSCHALT Zustand festgelegt.

Wenn *WCHAR* ein NULL-breit Zeichen ist, wird eine Sequenz, die zum Wiederherstellen des anfänglichen UMSCHALT Zustands erforderlich ist, bei Bedarf gespeichert, gefolgt vom NULL-Zeichen. *State* wird auf den ursprünglichen Konvertierungs Zustand festgelegt. Die **c32rtomb** -Funktion ist identisch, konvertiert aber ein UTF-32-Zeichen.

Wenn *mbchar* ein NULL-Zeiger ist, entspricht das Verhalten einem Aufrufe der Funktion, die einen internen Puffer für *mbchar* und ein breites NULL-Zeichen für *WCHAR*ersetzt.

Mit dem State Conversion State-Objekt können Sie nachfolgende Aufrufe dieser Funktion und anderer Neu startbarer Funktionen ausführen *, die den* UMSCHALT Zustand der multibyteausgabezeichen beibehalten. Die Ergebnisse sind nicht definiert, wenn Sie die Verwendung von Neu Start baren und nicht neu startbaren Funktionen kombinieren.

Verwenden Sie zum Konvertieren von UTF-16-Zeichen in nicht-UTF-8-Multibytezeichen die Funktionen [wcstomsb, _wcstombs_l](wcstombs-wcstombs-l.md), [wcstombs_s oder _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) .

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**c16rtomb**, **c32rtomb**|C, C++: \<uchar.h>|

Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../compatibility.md).

## <a name="see-also"></a>Siehe auch

[Daten Konvertierungs](../data-conversion.md)\
[Gebietsschema](../locale.md)\
[Interpretation von Multibyte-Zeichensequenzen](../interpretation-of-multibyte-character-sequences.md)\
[mbrtoc16, mbrtoc32](mbrtoc16-mbrtoc323.md)\
[wcrtomb](wcrtomb.md)\
[wcrtomb_s](wcrtomb-s.md)
