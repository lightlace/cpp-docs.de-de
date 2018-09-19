---
title: Segmentieren Sie Verweise in der Inlineassembly | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
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
ms.openlocfilehash: 792dda60407928aaf4a7d3fec2a61c0018b8b35a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676388"
---
# <a name="segment-references-in-inline-assembly"></a>Segmentverweise in der Inlineassembly

**Microsoft-spezifisch**

Sie müssen auf Segmente verweisen, nach Register statt über den Namen (den Segmentnamen `_TEXT` ist ungültig, z. B.). Segment überschreibungen müssen der Registrierung verwenden, in der explizit, wie ES: [BX].

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>