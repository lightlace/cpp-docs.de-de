---
title: Typen- und Variablengrößen in der Inlineassembly
ms.date: 08/30/2018
ms.topic: reference
f1_keywords:
- length
- Type
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
ms.openlocfilehash: 36c97ee866ca449e9bbcf514e464a13f24f12cd9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539099"
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>Typen- und Variablengrößen in der Inlineassembly

**Microsoft-spezifisch**

Die **Länge**, **Größe**, und **Typ** Operatoren haben eine begrenzte Bedeutung in der Inlineassembly. Sie können nicht mit überhaupt verwendet werden die `DUP` Operator (da Sie Daten mit MASM-Anweisungen und Operatoren definieren können). Jedoch können sie um die Größe von C- oder C++-Variablen oder Typen zu ermitteln:

- Die **Länge** Operator kann die Anzahl der Elemente in einem Array zurückgeben. Es gibt den Wert 1 für nicht-Array-Variablen zurück.

- Die **Größe** Operator kann die Größe einer C- oder C++-Variablen zurück. Eine Variable, die Größe ist das Produkt aus der **Länge** und **Typ**.

- Die **Typ** Operator kann die Größe des eine C- oder C++-Typ oder eine Variable zurückgeben. Wenn die Variable ein Array, **Typ** gibt die Größe eines einzelnen Elements des Arrays zurück.

Wenn das Programm ein 8-Element weist z. B. **Int** Array

```cpp
int arr[8];
```

die folgenden C "und" Assembly-Ausdrücke zu erhalten, die Größe des `arr` und die zugehörigen Elemente.

|__asm|C|Größe|
|-------------|-------|----------|
|**Länge** Arr|`sizeof`(Arr) /`sizeof`(arr[0])|8|
|**Größe** Arr|`sizeof`(Arr)|32|
|**Typ** Arr|`sizeof`(arr[0])|4|

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>