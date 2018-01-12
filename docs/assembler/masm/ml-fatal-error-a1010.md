---
title: ML-Schwerwiegender Fehler A1010 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1010
dev_langs: C++
helpviewer_keywords: A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b495fc2b8bd0e667dd7dae7e23347f6971ec4d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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