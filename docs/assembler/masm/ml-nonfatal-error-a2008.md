---
title: ML nicht schwerwiegende Fehler A2008 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2008
dev_langs: C++
helpviewer_keywords: A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a268fd3f82b96698d8e200486c2091cabfad95ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2008"></a>Nicht schwerwiegender ML-Fehler A2008
**Syntaxfehler:**  
  
 Ein Token an der aktuellen Position verursachte einen Syntaxfehler.  
  
 Eine der folgenden möglicherweise aufgetreten:  
  
-   Ein Punkt-Präfix wurde hinzugefügt oder in eine Direktive nicht angegeben.  
  
-   Ein reserviertes Wort (z. B. **C** oder **Größe**) wurde als Bezeichner verwendet.  
  
-   Eine Anweisung wurde verwendet, die nicht mit der aktuellen Auswahl der Prozessor oder Coprozessor verfügbar war.  
  
-   Ein Laufzeit-Vergleichsoperator (z. B. `==`) wurde in einer bedingten Assembly-Anweisung statt ein relationaler Operator verwendet (z. B. [EQ](../../assembler/masm/operator-eq.md)).  
  
-   Eine Anweisung oder in der Richtlinie wurden zu wenige Operanden zugewiesen:  
  
-   Es wurde eine veraltete-Direktive verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)