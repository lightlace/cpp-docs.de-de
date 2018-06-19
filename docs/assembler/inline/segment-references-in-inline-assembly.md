---
title: Segmentieren Sie Verweise in der Inlineassembly | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- references, inline assembly
- segment references in inline assembly
- inline assembly, segment references
- registers
- inline assembly, registers
- registers, inline assembly
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7add95852f751ed29dad8e0ba9577abd55fabaf
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32051475"
---
# <a name="segment-references-in-inline-assembly"></a>Segmentverweise in der Inlineassembly
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Sie müssen auf Segmente verweisen, nach Register statt über den Namen (den Segmentnamen `_TEXT` ist ungültig, z. B.). Segment Außerkraftsetzungen müssen verwenden Sie die Registrierung explizit, wie ES in: [BX].  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)