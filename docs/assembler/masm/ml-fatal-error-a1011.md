---
title: ML-Schwerwiegender Fehler A1011 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1011
dev_langs:
- C++
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 843d676cba61e0da5f917a48408e56e79abb9efd
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057202"
---
# <a name="ml-fatal-error-a1011"></a>Schwerwiegender ML-Fehler A1011
**Richtlinie muss im Kontrollblock**  
  
 Der Assembler wurde eine allgemeine Richtlinie, wo eine nicht erwartet wurde, gefunden. Eine der folgenden Direktiven wurde gefunden:  
  
-   [. ELSE](../../assembler/masm/dot-else.md) ohne [. IF](../../assembler/masm/dot-if.md)  
  
-   [. ENDIF](../../assembler/masm/dot-endif.md) ohne [. IF](../../assembler/masm/dot-if.md)  
  
-   [. ENDW](../../assembler/masm/dot-endw.md) ohne [. WHILE](../../assembler/masm/dot-while.md)  
  
-   [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md) ohne [. WIEDERHOLEN SIE DEN VORGANG](../../assembler/masm/dot-repeat.md)  
  
-   [. WEITERHIN](../../assembler/masm/dot-continue.md) ohne [. WÄHREND](../../assembler/masm/dot-while.md) oder [. WIEDERHOLEN SIE DEN VORGANG](../../assembler/masm/dot-repeat.md)  
  
-   [. UNTERBRECHEN](../../assembler/masm/dot-break.md) ohne [. WÄHREND](../../assembler/masm/dot-while.md) oder [. WIEDERHOLEN SIE DEN VORGANG](../../assembler/masm/dot-repeat.md)  
  
-   [. ELSE](../../assembler/masm/dot-else.md) folgenden `.ELSE`  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)