---
title: srand
ms.date: 01/02/2018
api_name:
- srand
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
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 03e2b87a37d1b520b6e2b32c2f756fea625eb9a2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957996"
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
