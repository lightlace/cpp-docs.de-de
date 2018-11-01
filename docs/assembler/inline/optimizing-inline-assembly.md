---
title: Optimieren der Inlineassembly
ms.date: 08/30/2018
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
ms.openlocfilehash: d4956ba12e0bc268d78a895e6cb1ec6e2059262a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538865"
---
# <a name="optimizing-inline-assembly"></a>Optimieren der Inlineassembly

**Microsoft-spezifisch**

Das Vorhandensein einer `__asm` Block in einer Funktion wirkt sich auf die Optimierung auf verschiedene Weise. Der Compiler nicht zuerst versucht, zur Optimierung der `__asm` -Block selbst. Was Sie in der Assemblysprache schreiben ist genau das, was Sie erhalten. Sekunde, die das Vorhandensein einer `__asm` Block wirkt sich auf die Variable Speicher registrieren. Der Compiler vermeidet Ablaufanalyse Variablen ein `__asm` blockieren, wenn Sie den Inhalt des Registers von geändert werden, würde die `__asm` Block. Schließlich sind einige weitere Optimierungen des gesamten Funktion durch die Aufnahme der Assemblysprache in einer Funktion betroffen.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>