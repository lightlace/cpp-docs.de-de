---
title: srand | Microsoft-Dokumentation
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: srand
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
f1_keywords: srand
dev_langs: C++
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
ms.workload: cplusplus
ms.openlocfilehash: 205dcb2ba7d61dff1286fd926e3f10cf2a162e9a
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
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

*Startwert*  
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
