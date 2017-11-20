---
title: EVEN- und ALIGN-Direktiven | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- align
- EVEN
dev_langs: C++
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5048e9f8c2991133ad0cf28720b9236232cc9337
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="even-and-align-directives"></a>EVEN- und ALIGN-Anweisungen
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Obwohl der Inlineassembler von den meisten MASM-makroanweisungen nicht unterstützt, unterstützt es `EVEN` und **AUSRICHTEN**. Diese Direktiven put **NOP** (kein Vorgang) Anweisungen in der Assemblycode nach Bedarf, um Bezeichnungen zu bestimmten Grenzen ausgerichtet. Dies wird Anweisung-Abrufvorgänge für einige Prozessoren effizienter.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)