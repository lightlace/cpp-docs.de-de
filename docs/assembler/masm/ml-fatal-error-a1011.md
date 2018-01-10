---
title: ML-Schwerwiegender Fehler A1011 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1011
dev_langs: C++
helpviewer_keywords: A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 470340e76897394e5b8ecb042ff97562b0c94c2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
  
-   [. ELSE](../../assembler/masm/dot-else.md) folgenden`.ELSE`  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)