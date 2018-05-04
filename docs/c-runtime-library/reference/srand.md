---
title: srand | Microsoft-Dokumentation
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2b527561e312ce9c50dce106a243d7e49a1d303
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="srand"></a>srand

Legt den Startwert für den pseudozufallszahlengenerator verwendet werden, indem Sie die **Rand** Funktion.

## <a name="syntax"></a>Syntax

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Parameter

*Ausgangswert* Ausgangswert für die pseudozufallszahlengenerierung

## <a name="remarks"></a>Hinweise

Die **Srand** -Funktion legt den Ausgangspunkt für das Generieren von pseudozufallsganzzahlen im aktuellen Thread fest. Um den Generator zum Erstellen von derselben Sequenz von Ergebnissen erneut zu initialisieren, rufen Sie die **Srand** Funktion, und verwenden Sie den gleichen *Ausgangswert* -Argument erneut. Jeder andere Wert für *Ausgangswert* definiert den Erzeuger auf einen anderen Startpunkt in der pseudozufallssequenz. **Rand** Ruft den pseudozufälligen Zahlen, die generiert werden. Aufrufen von **Rand** vor irgendeinem Aufruf von **Srand** generiert die gleiche Sequenz wie das Aufrufen **Srand** mit *Ausgangswert* übergeben als 1.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**srand**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [rand](rand.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
