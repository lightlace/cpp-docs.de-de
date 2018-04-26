---
title: mbrtoc16, mbrtoc323 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 842950535dd71ba678e00a3203df17625ab50a4d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

*Ziel*<br/>
Zeiger auf die **char16_t** oder **char32_t** entspricht, der das zu konvertierende multibyte-Zeichen. Wenn der Wert NULL ist, speichert die Funktion keinen Wert.

*Datenquelle*<br/>
Zeiger auf die zu konvertierende Multibyte-Zeichenfolge.

*max_bytes*<br/>
Die maximale Anzahl von Bytes in *Quelle* auf ein zu konvertierendes Zeichen untersucht. Dies muss ein Wert zwischen 1 und die Anzahl der Bytes, einschließlich eines eventuellen nullterminators, die im verbleibenden *Quelle*.

*state*<br/>
Zeiger auf eine **Mbstate_t** konvertierungszustandsobjekt verwendet, um die multibyte-Zeichenfolge auf einem oder mehreren Ausgabezeichen zu interpretieren.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg gibt den Wert des ersten erfüllten Bedingung, bestimmten aktuellen *Zustand* Wert:

|Wert|Bedingung|
|-----------|---------------|
|0|Das nächste *Max_bytes* oder weniger Zeichen aus konvertiert *Quelle* entsprechen dem breiten Nullzeichen, das den Wert gespeichert werden, wenn *Ziel* ist ungleich null.<br /><br /> *Status* enthält den ursprünglichen Umschaltzustand zurückgesetzt.|
|Zwischen 1 und *Max_bytes*(einschließlich)|Der zurückgegebene Wert ist die Anzahl der Bytes der *Quelle* , ein gültiges Multibytezeichen abgeschlossen. Das konvertierte Breitzeichen wird gespeichert, wenn *Ziel* ist ungleich null.|
|-3|Der nächste Breitzeichen, das aus einem vorherigen Aufruf der Funktion stammenden in gespeichert wurde *Ziel* Wenn *Ziel* ist ungleich null. Keine Bytes von *Quelle* durch diesen Aufruf an die Funktion verwendet werden.<br /><br /> Wenn *Quelle* verweist auf ein Multibytezeichen, die mehr als ein Breitzeichen (z. B. ein Ersatzzeichenpaar) darstellen, erfordert die *Zustand* Wert wird aktualisiert, sodass der nächste Funktionsaufruf schreibt  das zusätzliche Zeichen.|
|-2|Das nächste *Max_bytes* Bytes stellen ein unvollständiges, aber möglicherweise ungültig, multibyte-Zeichen dar. Kein Wert befindet sich in *Ziel*. Dieses Ergebnis kann auftreten, wenn *Max_bytes* 0 (null).|
|-1|Es ist ein Codierungsfehler aufgetreten. Das nächste *Max_bytes* oder weniger Bytes tragen nicht zu einem vollständigen und gültigen Multibytezeichen bei. Kein Wert befindet sich in *Ziel*.<br /><br /> **EILSEQ** befindet sich in **Errno** und der Konvertierungsstatus *Zustand* ist nicht angegeben.|

## <a name="remarks"></a>Hinweise

Die **mbrtoc16** Funktion liest bis zum *Max_bytes* Bytes vom *Quelle* die erste vollständige gültige Multibytezeichen, und speichert dann die entsprechende UTF-16 gefunden Zeichen in *Ziel*. Die Quellbytes werden gemäß dem Multibyte-Gebietsschema des aktuellen Threads interpretiert. Wenn das Multibytezeichen mehr als ein UTF-16-Ausgabezeichen, z. B. ein Ersatzzeichenpaar erfordert die *Status* festgelegt ist, speichern das nächste UTF-16-Zeichen in *Ziel* beim nächsten Aufruf von **mbrtoc16**. Die **mbrtoc32** -Funktion ist identisch, aber die Ausgabe wird als UTF-32-Zeichen gespeichert.

Wenn *Quelle* Null ist, diese return Funktionen das Äquivalent eines Aufrufs mit den Argumenten **NULL** für *Ziel*, **""** für *Quelle*, und 1 für *Max_bytes*. Die übergebenen Werte von *Ziel* und *Max_bytes* werden ignoriert.

Wenn *Quelle* ist ungleich null, die Funktion beginnt am Anfang der Zeichenfolge und untersucht bis zu *Max_bytes* Bytes bestimmen die Anzahl der Bytes, die zum Abschließen des nächsten multibytezeichens erforderlich einschließlich eventueller umschaltsequenzen. Wenn die untersuchten Bytes ein gültiges und vollständiges Multibytezeichen enthalten, konvertiert die Funktion das Zeichen in das bzw. die entsprechende(n) 16 Bit oder 32 Bit breite(n) Zeichen. Wenn *Ziel* nicht NULL ist, speichert die Funktion, die die erste (und möglicherweise einzige) ergebniszeichen im Ziel. Wenn weitere Ausgabezeichen erforderlich sind, wird ein Wert festgelegt, *Status*, sodass nachfolgende Aufrufe an die Funktion die zusätzlichen Zeichen ausgeben und den Wert-3 zurückgeben. Wenn keine weiteren Ausgabezeichen erforderlich sind, werden *Zustand* festgelegt ist, um den ursprünglichen Umschaltzustand zurückgesetzt.

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
