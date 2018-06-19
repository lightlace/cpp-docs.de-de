---
title: Optimieren der Inlineassembly | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: c494594e3b7c541487f34fd33359b0e31f73dd61
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050557"
---
# <a name="optimizing-inline-assembly"></a>Optimieren der Inlineassembly
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Das Vorhandensein einer `__asm` Block in einer Funktion wirkt sich auf die Optimierung auf verschiedene Weise. Der Compiler nicht versuchen Sie zunächst, Optimieren der `__asm` selbst zu blockieren. Was Sie in der Assemblysprache geschrieben ist genau erhalten Sie. Sekunde, die das Vorhandensein einer `__asm` Block wirkt sich auf Variablen Speicherung zu registrieren. Der Compiler vermeidet Ablaufanalyse Variablen über eine `__asm` blockieren, wenn die dort den Registerinhalt würde, durch geändert werden die `__asm` Block. Schließlich sind einige andere Funktion Wide-Optimierungen durch die Aufnahme der Assemblysprache in einer Funktion betroffen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)