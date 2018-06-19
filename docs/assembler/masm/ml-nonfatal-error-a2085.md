---
title: ML nicht schwerwiegende Fehler A2085 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2085
dev_langs:
- C++
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f0a014810679f0b48f79198b1335240f5cd6a8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32054275"
---
# <a name="ml-nonfatal-error-a2085"></a>Nicht schwerwiegender ML-Fehler A2085
**Anweisung oder die Registrierung, die im aktuellen CPU-Modus nicht akzeptiert.**  
  
 Es wurde versucht, eine Anweisung, Register oder Schlüsselwort, das für den aktuellen Prozessormodus ungültig war.  
  
 32-Bit-Register beispielsweise erfordern [.386](../../assembler/masm/dot-386.md) oder höher. -Steuerelement registriert wird, z. B. CR0 erfordern privilegierten Modus [.386P](../../assembler/masm/dot-386p.md) oder höher. Dieser Fehler wird auch generiert werden, für die **NEAR32**, **FAR32**, und **Flatfile** Schlüsselwörter, die erforderlich sind. **386** oder höher.  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)