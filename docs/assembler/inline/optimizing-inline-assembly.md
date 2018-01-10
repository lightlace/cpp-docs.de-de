---
title: Optimieren der Inlineassembly | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 21f6954ece6adcc60fbb3a8620dd427e7c21042a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="optimizing-inline-assembly"></a>Optimieren der Inlineassembly
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Das Vorhandensein einer `__asm` Block in einer Funktion wirkt sich auf die Optimierung auf verschiedene Weise. Der Compiler nicht versuchen Sie zunächst, Optimieren der `__asm` selbst zu blockieren. Was Sie in der Assemblysprache geschrieben ist genau erhalten Sie. Sekunde, die das Vorhandensein einer `__asm` Block wirkt sich auf Variablen Speicherung zu registrieren. Der Compiler vermeidet Ablaufanalyse Variablen über eine `__asm` blockieren, wenn die dort den Registerinhalt würde, durch geändert werden die `__asm` Block. Schließlich sind einige andere Funktion Wide-Optimierungen durch die Aufnahme der Assemblysprache in einer Funktion betroffen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)