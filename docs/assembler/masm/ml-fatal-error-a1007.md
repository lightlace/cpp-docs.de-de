---
title: ML-Schwerwiegender Fehler A1007 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1007
dev_langs:
- C++
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10b883fad01943cd8cff71b3da9dee66407ccc93
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32055728"
---
# <a name="ml-fatal-error-a1007"></a>Schwerwiegender ML-Fehler A1007
**Die Schachtelungsebene ist zu tief geschachtelt**  
  
 Der Assembler hat Schachtelungsebenen überschritten. Es sind maximal 20 Ebenen anders andernfalls.  
  
 Eine der folgenden wurde zu tief geschachtelt werden:  
  
-   Eine allgemeine Richtlinie z. B. [. IF](../../assembler/masm/dot-if.md), [. Wiederholen Sie die](../../assembler/masm/dot-repeat.md), oder [. WÄHREND](../../assembler/masm/dot-while.md).  
  
-   Die Strukturdefinition einer.  
  
-   Ein bedingter-Assemblydirektive.  
  
-   Die Definition einer Prozedur.  
  
-   Ein [PUSHCONTEXT](../../assembler/masm/pushcontext.md) Richtlinie (der Grenzwert ist 10).  
  
-   Eine Definition des Segments.  
  
-   Eine Includedatei.  
  
-   Ein Makro.  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)