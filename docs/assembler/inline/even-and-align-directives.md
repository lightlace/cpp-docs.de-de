---
title: EVEN- und ALIGN-Direktiven | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- align
- EVEN
dev_langs:
- C++
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a43425a4038ffb140eeaa0a9d111a39fc5c11ff0
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057954"
---
# <a name="even-and-align-directives"></a>EVEN- und ALIGN-Anweisungen
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Obwohl der Inlineassembler von den meisten MASM-makroanweisungen nicht unterstützt, unterstützt es `EVEN` und **AUSRICHTEN**. Diese Direktiven put **NOP** (kein Vorgang) Anweisungen in der Assemblycode nach Bedarf, um Bezeichnungen zu bestimmten Grenzen ausgerichtet. Dies wird Anweisung-Abrufvorgänge für einige Prozessoren effizienter.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)