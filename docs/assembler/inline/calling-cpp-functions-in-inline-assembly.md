---
title: Aufrufen von C++-Funktionen in der Inlineassembly
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
ms.openlocfilehash: 666f7b2a59f0d48a14be54a439b6402f2a4d3128
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458224"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Aufrufen von C++-Funktionen in der Inlineassembly

**Microsoft-spezifisch**

Ein `__asm` Block kann nur globale C++-Funktionen, die nicht überladen werden aufrufen. Wenn Sie eine globale überladene C++-Funktion oder eine C++-Memberfunktion aufrufen, gibt der Compiler einen Fehler aus.

Sie können auch alle mit deklarierten Funktionen aufrufen **Extern "C"** Verknüpfung. Dies ermöglicht eine `__asm` -Block innerhalb eines C++-Programms den Funktionen der C-Bibliothek aufrufen, da es sich bei die standardmäßigen Headerdateien deklarieren, die Bibliotheksfunktionen haben **Extern "C"** Verknüpfung.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>