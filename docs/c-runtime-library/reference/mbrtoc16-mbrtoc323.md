---
title: mbrtoc16, mbrtoc323
ms.date: 11/04/2016
api_name:
- mbrtoc16
- mbrtoc32
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
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
ms.openlocfilehash: 52bcec5911fdc2ecbb073ae0042777aa4eb2b963
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952444"
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

*entwickelt*<br/>
Ein Zeiger auf die **char16_t** -oder **char32_t** -Entsprechung des zu konvertierenden multibytezeichens. Wenn der Wert NULL ist, speichert die Funktion keinen Wert.

*source*<br/>
Zeiger auf die zu konvertierende Multibyte-Zeichenfolge.

*max_bytes*<br/>
Die maximale Anzahl von Bytes in der *Quelle* , die für ein zu konvertierendes Zeichen untersucht werden soll. Dabei sollte es sich um einen Wert zwischen 1 und der Anzahl von Bytes handeln, einschließlich eines beliebigen null-Terminator, der in der *Quelle*verbleiben.

*state*<br/>
Ein Zeiger auf ein **mbstate_t** -Konvertierungs Zustands Objekt, das verwendet wird, um die Multibytezeichenfolge auf ein oder mehrere Ausgabe Zeichen

## <a name="return-value"></a>Rückgabewert

Bei Erfolg wird der Wert der ersten dieser Bedingungen mit dem aktuellen *Zustands* Wert zurückgegeben:

|Wert|Bedingung|
|-----------|---------------|
|0|Die nächsten *max_bytes* oder weniger Zeichen, die aus der *Quelle* konvertiert werden, entsprechen dem NULL-breit Zeichen. Hierbei handelt es sich um den Wert, der bei nicht-NULL- *Ziel*<br /><br /> *State* enthält den anfänglichen Verschiebungs Zustand.|
|Zwischen 1 und *max_bytes*, einschließlich|Der zurückgegebene Wert ist die Anzahl der Bytes der *Quelle* , die ein gültiges Multibytezeichen vervollständigen. Das konvertierte breit Zeichen wird gespeichert, wenn *Destination* nicht NULL ist.|
|-3|Das nächste breit Zeichen, das sich aus einem vorherigen Aufrufe der Funktion ergibt, wurde im *Ziel* gespeichert, wenn *Destination* nicht NULL ist. Von diesem Aufrufe der-Funktion werden keine Bytes aus der *Quelle* verwendet.<br /><br /> Wenn die *Quelle* auf ein Multibytezeichen verweist, für das mehr als ein breit Zeichen erforderlich ist (z. b. ein Ersatz Zeichenpaar), wird der *Zustands* Wert aktualisiert, sodass der nächste Funktions aufrufdas zusätzliche Zeichen ausgibt.|
|-2|Die nächsten *max_bytes* Bytes stellen ein unvollständiges, aber potenziell gültiges Multibytezeichen dar. Es ist kein Wert im *Ziel*gespeichert. Dieses Ergebnis kann auftreten, wenn *max_bytes* 0 (null) ist.|
|-1|Es ist ein Codierungsfehler aufgetreten. Die nächsten *max_bytes* oder weniger Bytes tragen nicht zu einem kompletten und gültigen Multibytezeichen bei. Es ist kein Wert im *Ziel*gespeichert.<br /><br /> **EILSEQ** wird in **errno** gespeichert, und der *Zustand* des Konvertierungs Zustands ist nicht angegeben.|

## <a name="remarks"></a>Hinweise

Die **mbrtoc16** -Funktion liest bis zu *max_bytes* Bytes aus der *Quelle* , um das erste komplette, gültige Multibytezeichen zu finden, und speichert dann das entsprechende UTF-16-Zeichen im *Ziel*. Die Quellbytes werden gemäß dem Multibyte-Gebietsschema des aktuellen Threads interpretiert. Wenn für das Multibytezeichen mehr als ein UTF-16-Ausgabe Zeichen erforderlich ist (z. b. ein Ersatz Zeichenpaar), wird der *Zustands* Wert so festgelegt, dass beim nächsten **mbrtoc16**-Aufrufe das nächste UTF-16-Zeichen im *Ziel* gespeichert wird. Die **mbrtoc32** -Funktion ist identisch, die Ausgabe wird jedoch als UTF-32-Zeichen gespeichert.

Wenn die *Quelle* NULL ist, geben diese Funktionen das Äquivalent eines Aufrufes mit Argumenten **von NULL** für das *Ziel*, **""** für die *Quelle*und 1 für *max_bytes*zurück. Die bestandenen Werte von *Destination* und *max_bytes* werden ignoriert.

Wenn die *Quelle* nicht NULL ist, beginnt die Funktion am Anfang der Zeichenfolge und überprüft bis zu *max_bytes* bytes, um die Anzahl der Bytes zu bestimmen, die zum Vervollständigen des nächsten multibytezeichens erforderlich sind, einschließlich der Verschiebe Sequenzen. Wenn die untersuchten Bytes ein gültiges und vollständiges Multibytezeichen enthalten, konvertiert die Funktion das Zeichen in das bzw. die entsprechende(n) 16 Bit oder 32 Bit breite(n) Zeichen. Wenn *Destination* nicht NULL ist, speichert die Funktion das erste (und möglicherweise einzige) Ergebnis Zeichen im Ziel. Wenn zusätzliche Ausgabe Zeichen erforderlich sind, wird ein Wert im *Zustand*festgelegt, sodass nachfolgende Aufrufe der Funktion die zusätzlichen Zeichen ausgeben und den Wert-3 zurückgeben. Wenn keine weiteren Ausgabe Zeichen erforderlich sind, wird *State* auf den anfänglichen Verschiebungs Zustand festgelegt.

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
