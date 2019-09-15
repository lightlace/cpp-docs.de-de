---
title: c16rtomb, c32rtomb
ms.date: 01/22/2018
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
ms.openlocfilehash: a16effe48442ccbb5144b57ead2fb15c908fe898
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943431"
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb

Konvertiert ein UTF-16- oder UTF-32-Breitzeichen in ein Multibytezeichen im aktuellen Gebietsschema.

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

*mbchar*<br/>
Zeiger auf ein Array zum Speichern des in Multibyte konvertierten Zeichens.

*wchar*<br/>
Ein zu konvertierendes Breitzeichen.

*state*<br/>
Ein Zeiger auf ein **mbstate_t** -Objekt.

## <a name="return-value"></a>Rückgabewert

Die Anzahl der im Array Objekt *mbchar*gespeicherten Bytes, einschließlich der Verschiebe Sequenzen. Wenn *WCHAR* kein gültiges breit Zeichen ist, wird der Wert (**size_t**) (-1) zurückgegeben, **errno** ist auf **EILSEQ**festgelegt, und der Wert des *Zustands* ist nicht angegeben.

## <a name="remarks"></a>Hinweise

Die **c16rtomb** -Funktion konvertiert das UTF-16-Zeichen *WCHAR* in die entsprechende Multibytezeichen-schmale Zeichen Sequenz im aktuellen Gebiets Schema. Wenn *mbchar* kein NULL-Zeiger ist, speichert die Funktion die konvertierte Sequenz im Array Objekt, auf das von *mbchar*gezeigt wird. Bis zu **MB_CUR_MAX** Bytes werden in *mbchar*gespeichert, und *State* wird auf den resultierenden Multibytezeichen-UMSCHALT Zustand festgelegt.    Wenn *WCHAR* ein NULL-breit Zeichen ist, wird eine Sequenz gespeichert, die zum Wiederherstellen des anfänglichen Verschiebungs Zustands erforderlich ist, wenn erforderlich, gefolgt vom NULL-Zeichen, und *State* wird auf den ursprünglichen Konvertierungs Zustand festgelegt. Die **c32rtomb** -Funktion ist identisch, konvertiert aber ein UTF-32-Zeichen.

Wenn *mbchar* ein NULL-Zeiger ist, entspricht das Verhalten einem Aufrufe der Funktion, die einen internen Puffer für *mbchar* und ein breites NULL-Zeichen für *WCHAR*ersetzt.

Mit dem State Conversion State-Objekt können Sie nachfolgende Aufrufe dieser Funktion und anderer Neu startbarer Funktionen ausführen *, die den* UMSCHALT Zustand der multibyteausgabezeichen beibehalten. Die Ergebnisse sind nicht definiert, wenn Sie die Verwendung von Neu Start baren und nicht neu startbaren Funktionen kombinieren, oder wenn ein Aufruf von **setlocale** zwischen Neu Start baren Funktionsaufrufen erfolgt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**c16rtomb**, **c32rtomb**|C, C++: \<uchar.h>|

Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtoc16, mbrtoc32](mbrtoc16-mbrtoc323.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
