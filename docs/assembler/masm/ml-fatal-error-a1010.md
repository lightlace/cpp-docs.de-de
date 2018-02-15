---
title: ML-Schwerwiegender Fehler A1010 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A1010
dev_langs:
- C++
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 553071ff10688f0b49909b16c8c60d95899247d1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="ml-fatal-error-a1010"></a>Schwerwiegender ML-Fehler A1010
**nicht übereinstimmende Block Schachtelung:**  
  
 Eine Block beginnt verfügte nicht über ein zugehöriges End oder eine Block End verfügte nicht über eine entsprechende beginnt. Eine der folgenden möglicherweise beteiligt sind:  
  
-   Eine allgemeine Richtlinie z. B. [. IF](../../assembler/masm/dot-if.md), [. Wiederholen Sie die](../../assembler/masm/dot-repeat.md), oder [. WÄHREND](../../assembler/masm/dot-while.md).  
  
-   Ein bedingter-Assemblydirektive wie z. B. [IF](../../assembler/masm/if-masm.md), [wiederholen](../../assembler/masm/repeat.md), oder **während**.  
  
-   Eine Struktur oder Union-Definition.  
  
-   Die Definition einer Prozedur.  
  
-   Eine Definition des Segments.  
  
-   Ein [POPCONTEXT](../../assembler/masm/popcontext.md) Richtlinie.  
  
-   Eine bedingte-Assembly, z. B. die Richtlinie ein [ELSE](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md), oder **ENDIF** ohne ein passendes [IF](../../assembler/masm/if-masm.md).  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)