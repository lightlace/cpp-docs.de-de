---
title: srand
ms.date: 01/02/2018
apiname:
- srand
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
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- srand
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.openlocfilehash: d74ae4cbec5a76df48bb2b56acab7329e6cf8aa5
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927402"
---
# <a name="srand"></a>srand

Legt den Startwert für den von der **Rand** -Funktion verwendeten Pseudo Zufalls Number-Generator fest.

## <a name="syntax"></a>Syntax

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Parameter

*säen*<br/>
Startwert für die Pseudozufallszahlengenerierung

## <a name="remarks"></a>Hinweise

Die **srand** -Funktion legt den Ausgangspunkt für das Erstellen einer Reihe von Pseudo Zufalls-Ganzzahlen im aktuellen Thread fest. Um den Generator erneut zu initialisieren, um dieselbe Sequenz von Ergebnissen zu erstellen, rufen Sie die **srand** -Funktion auf, und verwenden Sie das gleiche *Seed* -Argument erneut. Jeder andere Wert für *Seed* legt den Generator auf einen anderen Startpunkt in der Pseudo Zufalls-Sequenz fest. **Rand** Ruft die zu Generier baren Pseudo Zufalls-Zahlen ab. Der Aufruf von **Rand** vor jedem Aufruf von **srand** generiert dieselbe Sequenz wie der *Aufruf von* **srand** mit einem als 1 bestandenen Ausgangswerten.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**srand**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [rand](rand.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
