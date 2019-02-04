---
title: c16rtomb, c32rtomb
ms.date: 01/22/2018
apiname:
- c16rtomb
- c32rtomb
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
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
ms.openlocfilehash: ad58184c7bab6f95a842bda5f9eb545f09434a3e
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702777"
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
Ein Zeiger auf ein **Mbstate_t** Objekt.

## <a name="return-value"></a>Rückgabewert

Die Anzahl der Bytes, die in Arrayobjekt gespeicherten *Mbchar*, einschließlich eventueller umschaltsequenzen. Wenn *Wchar* ist kein gültiges Breitzeichen ist, den Wert (**"size_t"**)(-1) zurückgegeben, **Errno** nastaven NA hodnotu **EILSEQ**, und der Wert der *Zustand* ist nicht angegeben.

## <a name="remarks"></a>Hinweise

Die **c16rtomb** -Funktion konvertiert das UTF-16-Zeichen *Wchar* der Sequenz entspricht multibytesequenz aus halbbreiten Zeichen im aktuellen Gebietsschema. Wenn *Mbchar* ist kein null-Zeiger, speichert die Funktion, die die konvertierte Sequenz im Arrayobjekt verweist *Mbchar*. Bis zu **MB_CUR_MAX** Bytes befinden sich im *Mbchar*, und *Zustand* auf den resultierenden multibyte-UMSCHALT-Status festgelegt ist.    Wenn *Wchar* ist ein null-Breitzeichen, eine Sequenz, die zum Wiederherstellen der ursprünglichen UMSCHALT-Status, gespeichert wird, wenn erforderlich, gefolgt von Null-Zeichen und *Zustand* auf den ursprünglichen Konvertierungsstatus festgelegt ist. Die **c32rtomb** Funktion ist identisch, aber ein UTF-32-Zeichen konvertiert.

Wenn *Mbchar* ein null-Zeiger ist das Verhalten ist gleichbedeutend mit einem Aufruf an die Funktion, die einen internen Puffer ersetzt *Mbchar* und ein Null-Breitzeichen für *Wchar*.

Die *Zustand* -konvertierungsstatusobjekt ermöglicht Ihnen, aufeinander folgende Aufrufe dieser Funktion und anderer erneut startbaren Funktionen, die die UMSCHALT-Status der multibyteausgabezeichen zu verwalten. Wenn Sie die Verwendung von erneut startbare und nicht startbare Funktionen gemischt oder wenn ein Aufruf von sind die Ergebnisse undefiniert **Setlocale** erfolgt zwischen zwei aufrufen.

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
