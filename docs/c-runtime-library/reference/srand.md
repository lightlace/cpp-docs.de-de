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
ms.openlocfilehash: 6545d4eba6c17fd55bb2b8cf23fb0319d1c96bee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354885"
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

*seed*<br/>
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
