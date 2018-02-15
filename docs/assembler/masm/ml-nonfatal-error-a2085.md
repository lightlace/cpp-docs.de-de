---
title: ML nicht schwerwiegende Fehler A2085 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A2085
dev_langs:
- C++
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29d0d58e5cd65c16c848b3cc05e10b9f57488639
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="ml-nonfatal-error-a2085"></a>Nicht schwerwiegender ML-Fehler A2085
**Anweisung oder die Registrierung, die im aktuellen CPU-Modus nicht akzeptiert.**  
  
 Es wurde versucht, eine Anweisung, Register oder Schlüsselwort, das für den aktuellen Prozessormodus ungültig war.  
  
 32-Bit-Register beispielsweise erfordern [.386](../../assembler/masm/dot-386.md) oder höher. -Steuerelement registriert wird, z. B. CR0 erfordern privilegierten Modus [.386P](../../assembler/masm/dot-386p.md) oder höher. Dieser Fehler wird auch generiert werden, für die **NEAR32**, **FAR32**, und **Flatfile** Schlüsselwörter, die erforderlich sind. **386** oder höher.  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)