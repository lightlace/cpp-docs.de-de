---
title: Verwenden von Operatoren in __asm-Blöcken
ms.date: 08/30/2018
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
ms.openlocfilehash: a871c19942252bf6a1a4901f8854b7b759700cd9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432798"
---
# <a name="using-operators-in-asm-blocks"></a>Verwenden von Operatoren in __asm-Blöcken

**Microsoft-spezifisch**

Ein `__asm` Block kann nicht C- oder C++ bestimmte Operatoren verwenden, z. B. die **<<** Operator. Allerdings Operatoren von und gemeinsam verwendeten C MASM, z. B. die \* Assemblysprache Operatoren Operator interpretiert werden. Beispielsweise außerhalb einer `__asm` blockieren, eckige Klammern (**[]**) interpretiert werden, wie der einschließende Arrayfeldindizes, die C automatisch auf die Größe eines Elements im Array wird. Innerhalb einer `__asm` Block, sie werden als den MASM-Index-Operator, der führt zu einen-Byte-Offset von Datenobjekt oder Bezeichnung (nicht nur ein Array) betrachtet. Der folgende Code veranschaulicht den Unterschied:

```cpp
int array[10];

__asm mov array[6], bx ;  Store BX at array+6 (not scaled)

array[6] = 0;         /* Store 0 at array+24 (scaled) */
```

Der erste Verweis auf `array` wird nicht skaliert werden, aber die zweite ist. Beachten Sie, mit denen Sie die **Typ** Operator, um die Skalierung zu erzielen auf Grundlage einer Konstante. Die folgenden Anweisungen sind beispielsweise äquivalent:

```cpp
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24

array[6] = 0;                   /* Store 0 at array + 24 */
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>