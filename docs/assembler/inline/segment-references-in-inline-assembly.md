---
title: Segmentverweise in der Inlineassembly
ms.date: 08/30/2018
helpviewer_keywords:
- references, inline assembly
- segment references in inline assembly
- inline assembly, segment references
- registers
- inline assembly, registers
- registers, inline assembly
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
ms.openlocfilehash: 5c07fa897da23a55f376a20e7588c8c8c269d1a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167373"
---
# <a name="segment-references-in-inline-assembly"></a>Segmentverweise in der Inlineassembly

**Microsoft-spezifisch**

Sie müssen auf Segmente verweisen, nach Register statt über den Namen (den Segmentnamen `_TEXT` ist ungültig, z. B.). Segment überschreibungen müssen der Registrierung verwenden, in der explizit, wie ES: [BX].

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>