---
title: Optimieren der Inlineassembly | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49660bdc6d2eb84e6e1bbaeb5ebf0d57e484e9e1
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687875"
---
# <a name="optimizing-inline-assembly"></a>Optimieren der Inlineassembly

**Microsoft-spezifisch**

Das Vorhandensein einer `__asm` Block in einer Funktion wirkt sich auf die Optimierung auf verschiedene Weise. Der Compiler nicht zuerst versucht, zur Optimierung der `__asm` -Block selbst. Was Sie in der Assemblysprache schreiben ist genau das, was Sie erhalten. Sekunde, die das Vorhandensein einer `__asm` Block wirkt sich auf die Variable Speicher registrieren. Der Compiler vermeidet Ablaufanalyse Variablen ein `__asm` blockieren, wenn Sie den Inhalt des Registers von geändert werden, würde die `__asm` Block. Schließlich sind einige weitere Optimierungen des gesamten Funktion durch die Aufnahme der Assemblysprache in einer Funktion betroffen.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>