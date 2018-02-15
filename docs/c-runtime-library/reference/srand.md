---
title: srand | Microsoft-Dokumentation
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4cc76b80ca6c01d6512c69cc13fb0934e79b6ae5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="srand"></a>srand

Legt den Startwert für den pseudozufallszahlengenerator verwendet werden, indem Sie die `rand` Funktion.

## <a name="syntax"></a>Syntax

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Parameter

*seed*  
Startwert für die Pseudozufallszahlengenerierung

## <a name="remarks"></a>Hinweise

Die `srand`-Funktion legt den Ausgangspunkt für das Generieren von Pseudozufallsganzzahlen im aktuellen Thread fest. Um den Generator zum Erstellen von derselben Sequenz von Ergebnissen erneut zu initialisieren, rufen Sie die `srand` Funktion, und verwenden Sie den gleichen *Ausgangswert* -Argument erneut. Jeder andere Wert für *Ausgangswert* definiert den Erzeuger auf einen anderen Startpunkt in der pseudozufallssequenz. `rand` ruft die generierten Pseudozufallszahlen ab. Aufrufen von `rand` vor irgendeinem Aufruf von `srand` generiert die gleiche Sequenz wie das Aufrufen `srand` mit *Ausgangswert* übergeben als 1.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`srand`|\<stdlib.h>|

Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [rand](../../c-runtime-library/reference/rand.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)  
[rand](../../c-runtime-library/reference/rand.md)  
