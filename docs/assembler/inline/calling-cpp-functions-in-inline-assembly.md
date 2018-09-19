---
title: Aufrufen von C++-Funktionen in der Inlineassembly | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4717ae24dc1a0b6f51f7a00f68f6569c2f988c65
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678943"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Aufrufen von C++-Funktionen in der Inlineassembly

**Microsoft-spezifisch**

Ein `__asm` Block kann nur globale C++-Funktionen, die nicht überladen werden aufrufen. Wenn Sie eine globale überladene C++-Funktion oder eine C++-Memberfunktion aufrufen, gibt der Compiler einen Fehler aus.

Sie können auch alle mit deklarierten Funktionen aufrufen **Extern "C"** Verknüpfung. Dies ermöglicht eine `__asm` -Block innerhalb eines C++-Programms den Funktionen der C-Bibliothek aufrufen, da es sich bei die standardmäßigen Headerdateien deklarieren, die Bibliotheksfunktionen haben **Extern "C"** Verknüpfung.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>