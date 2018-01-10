---
title: ML nicht schwerwiegende Fehler A2085 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2085
dev_langs: C++
helpviewer_keywords: A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f987b775c13b0e477fd5c1d215d556069535a0fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2085"></a>Nicht schwerwiegender ML-Fehler A2085
**Anweisung oder die Registrierung, die im aktuellen CPU-Modus nicht akzeptiert.**  
  
 Es wurde versucht, eine Anweisung, Register oder Schlüsselwort, das für den aktuellen Prozessormodus ungültig war.  
  
 32-Bit-Register beispielsweise erfordern [.386](../../assembler/masm/dot-386.md) oder höher. -Steuerelement registriert wird, z. B. CR0 erfordern privilegierten Modus [.386P](../../assembler/masm/dot-386p.md) oder höher. Dieser Fehler wird auch generiert werden, für die **NEAR32**, **FAR32**, und **Flatfile** Schlüsselwörter, die erforderlich sind. **386** oder höher.  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)