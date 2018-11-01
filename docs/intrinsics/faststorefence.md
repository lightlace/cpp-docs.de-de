---
title: __faststorefence
ms.date: 11/04/2016
f1_keywords:
- __faststorefence_cpp
- __faststorefence
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
ms.openlocfilehash: 8a90dd61e0017788a91d8ff2eccbae9d12143619
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650644"
---
# <a name="faststorefence"></a>__faststorefence

**Microsoft-spezifisch**

Stellt sicher, dass jeder vorhergehende Speicherverweis, einschließlich Speicherverweisen zum Laden und Speichern, vor jedem nachfolgenden Speicherverweis global sichtbar ist.

## <a name="syntax"></a>Syntax

```
void __faststorefence();
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__faststorefence`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Erzeugt eine Anweisungssequenz für eine Arbeitsspeicherbarriere für den gesamten Arbeitsspeicher, die sicherstellt, dass Lade- und Speichervorgänge, die vor dem systeminternen Vorgang ausgegeben wurden, global sichtbar sind, bevor die Ausführung fortgesetzt wird. Die Wirkung ist mit dem systeminternen `_mm_mfence` auf allen x64-Plattformen vergleichbar, aber schneller.

Auf der AMD64-Plattform generiert diese Routine eine Anweisung, die eine Speicherumgrenzung schneller erstellt als die `sfence`-Anweisung. Verwenden Sie bei zeitkritischem Code diese systeminterne Anweisung anstelle von `_mm_sfence` nur auf AMD64-Plattformen. Auf Intel x64-Plattformen ist die `_mm_sfence`-Anweisung schneller.

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)