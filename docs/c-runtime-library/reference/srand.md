---
title: srand
ms.date: 1/02/2018
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
ms.openlocfilehash: e1670c030d8f073d928ccf23f38ac4b611e68632
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530220"
---
# <a name="srand"></a>srand

Legt den Startwert für den pseudozufallszahlengenerator ein, die die **Rand** Funktion.

## <a name="syntax"></a>Syntax

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Parameter

*Startwert*<br/>
Startwert für die Pseudozufallszahlengenerierung

## <a name="remarks"></a>Hinweise

Die **Srand** Funktion legt den Ausgangspunkt für das Generieren von pseudozufallsganzzahlen im aktuellen Thread fest. Aufrufen, um den Generators zum Erstellen der gleichen Reihenfolge der Ergebnisse erneut zu initialisieren, die **Srand** Funktion, und verwenden Sie den gleichen *Ausgangswert* -Argument erneut. Jeder andere Wert für *Ausgangswert* des Generators auf einen anderen Startpunkt in der pseudozufallssequenz festgelegt. **Rand** Ruft ab, der Pseudozufallszahlen, die generiert werden. Aufrufen von **Rand** vor dem Aufruf **Srand** generiert die gleiche Sequenz wie das Aufrufen **Srand** mit *Ausgangswert* übergeben als 1.

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
