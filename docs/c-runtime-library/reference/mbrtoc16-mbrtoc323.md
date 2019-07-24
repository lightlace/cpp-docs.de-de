---
title: mbrtoc16, mbrtoc323
ms.date: 11/04/2016
apiname:
- mbrtoc16
- mbrtoc32
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
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
ms.openlocfilehash: f8573ac321772d19141be0228891b290ba48b217
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331583"
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16, mbrtoc32

Übersetzt das erste Multibytezeichen in einer schmalen Zeichenfolge in das entsprechende UTF-16- oder UTF-32-Zeichen.

## <a name="syntax"></a>Syntax

```C
size_t mbrtoc16(
   char16_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);

size_t mbrtoc32(
   char32_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);
```

### <a name="parameters"></a>Parameter

*destination*<br/>
Zeiger auf die **char16_t** oder **char32_t** entspricht, der die zu konvertierenden multibytezeichens. Wenn der Wert NULL ist, speichert die Funktion keinen Wert.

*source*<br/>
Zeiger auf die zu konvertierende Multibyte-Zeichenfolge.

*max_bytes*<br/>
Die maximale Anzahl von Bytes in *Quelle* auf ein zu konvertierendes Zeichen untersucht. Dies muss ein Wert zwischen 1 und die Anzahl der Bytes, einschließlich eines eventuellen nullterminators, die im verbleibenden *Quelle*.

*state*<br/>
Zeiger auf eine **Mbstate_t** konvertierungszustandsobjekt verwendet, um die multibyte-Zeichenfolge zu einem oder mehreren Ausgabezeichen zu interpretieren.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg wird den Wert des ersten dieser Bedingungen, die angewendet werden, da der aktuelle *Zustand* Wert:

|Wert|Bedingung|
|-----------|---------------|
|0|Die nächste *Max_bytes* oder weniger Zeichen konvertiert wird, von *Quelle* entsprechen dem breiten Nullzeichen, das den Wert gespeichert werden, wenn *Ziel* nicht null ist.<br /><br /> *Status* enthält den ursprünglichen Umschaltzustand zurückgesetzt.|
|Zwischen 1 und *Max_bytes*(einschließlich)|Der zurückgegebene Wert ist die Anzahl der Bytes der *Quelle* , ein gültiges Multibytezeichen abgeschlossen. Das konvertierte Breitzeichen wird gespeichert, wenn *Ziel* nicht null ist.|
|-3|Das nächste Breitzeichen, das aus einem vorherigen Aufruf an die Funktion gespeichert wurden *Ziel* Wenn *Ziel* nicht null ist. Keine Bytes von *Quelle* durch diesen Aufruf an die Funktion verwendet werden.<br /><br /> Wenn *Quelle* verweist auf ein Multibytezeichen, die mehr als ein Breitzeichen (z. B. ein Ersatzzeichenpaar) darstellen, erfordert die *Zustand* Wert wird aktualisiert, sodass der nächste Funktionsaufruf schreibt  das zusätzliche Zeichen.|
|-2|Die nächste *Max_bytes* Bytes stellen ein unvollständiges, aber möglicherweise ungültig, die multibyte-Zeichen. Kein Wert befindet sich in *Ziel*. Dieses Ergebnis kann auftreten, wenn *Max_bytes* ist 0 (null).|
|-1|Es ist ein Codierungsfehler aufgetreten. Die nächste *Max_bytes* oder weniger Bytes tragen nicht in einer vollständigen und gültigen Multibytezeichen. Kein Wert befindet sich in *Ziel*.<br /><br /> **EILSEQ** befindet sich in **Errno** und der Konvertierungsstatus *Zustand* ist nicht angegeben.|

## <a name="remarks"></a>Hinweise

Die **mbrtoc16** Funktion liest bis zum *Max_bytes* Bytes vom *Quelle* um die erste vollständige gültige Multibytezeichen und speichert die entsprechende UTF-16 suchen Zeichen in *Ziel*. Die Quellbytes werden gemäß dem Multibyte-Gebietsschema des aktuellen Threads interpretiert. Wenn das Multibytezeichen mehr als ein UTF-16-Ausgabezeichen, z. B. ein Ersatzzeichenpaar, erfordert die *Zustand* festgelegt ist, speichern das nächste UTF-16-Zeichen im *Ziel* beim nächsten Aufruf von **mbrtoc16**. Die **mbrtoc32** -Funktion ist identisch, aber die Ausgabe wird als UTF-32-Zeichen gespeichert.

Wenn *Quelle* Null ist, diese return Funktionen das Äquivalent eines Aufrufs wurde mit der Argumente der **NULL** für *Ziel*, **""** für *Quelle*, und 1 für *Max_bytes*. Die übergebenen Werte von *Ziel* und *Max_bytes* werden ignoriert.

Wenn *Quelle* ist nicht null ist, die Funktion beginnt am Anfang der Zeichenfolge und untersucht bis zu *Max_bytes* Bytes, um die Anzahl der Bytes, die zum Abschließen des nächsten multibytezeichens erforderlich zu bestimmen, einschließlich eventueller umschaltsequenzen. Wenn die untersuchten Bytes ein gültiges und vollständiges Multibytezeichen enthalten, konvertiert die Funktion das Zeichen in das bzw. die entsprechende(n) 16 Bit oder 32 Bit breite(n) Zeichen. Wenn *Ziel* ist nicht null ist, speichert die Funktion, die die erste (und möglicherweise einzige) ergebniszeichen im Ziel. Wenn weitere Ausgabezeichen erforderlich sind, wird ein Wert festgelegt, *Zustand*, sodass nachfolgende Aufrufe an die Funktion die zusätzlichen Zeichen ausgeben und den Wert-3 zurückgeben. Wenn keine weiteren Ausgabezeichen erforderlich sind *Zustand* festgelegt ist, um den ursprünglichen Umschaltzustand zurückgesetzt.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**mbrtoc16**, **mbrtoc32**|\<uchar.h>|\<cuchar>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[c16rtomb, c32rtomb](c16rtomb-c32rtomb1.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbsrtowcs](mbsrtowcs.md)<br/>
[mbsrtowcs_s](mbsrtowcs-s.md)<br/>
