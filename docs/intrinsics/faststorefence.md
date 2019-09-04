---
title: __faststorefence
ms.date: 09/02/2019
f1_keywords:
- __faststorefence_cpp
- __faststorefence
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
ms.openlocfilehash: d11a20666612fe1bca22f5d46b93e898dae375f6
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222178"
---
# <a name="__faststorefence"></a>__faststorefence

**Microsoft-spezifisch**

Stellt sicher, dass jeder vorhergehende Speicherverweis, einschließlich Speicherverweisen zum Laden und Speichern, vor jedem nachfolgenden Speicherverweis global sichtbar ist.

## <a name="syntax"></a>Syntax

```C
void __faststorefence();
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__faststorefence`|x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Generiert eine vollständige Arbeitsspeicher Barriere-Anweisungs Sequenz, die Lade-und Speichervorgänge garantiert, die ausgegeben werden, bevor die systeminterne Funktion vor der Ausführung von Die Wirkung ist mit dem systeminternen `_mm_mfence` auf allen x64-Plattformen vergleichbar, aber schneller.

Auf der AMD64-Plattform generiert diese Routine eine Anweisung, die eine Speicherumgrenzung schneller erstellt als die `sfence`-Anweisung. Verwenden Sie bei zeitkritischem Code diese systeminterne Anweisung anstelle von `_mm_sfence` nur auf AMD64-Plattformen. Auf Intel x64-Plattformen ist die `_mm_sfence`-Anweisung schneller.

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
