---
title: 2.7.2.3 Lastprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08f331862d6e48b1c0882382285ddffa9699e79c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="2723-lastprivate"></a>2.7.2.3 lastprivate
Die `lastprivate` -Klausel bietet eine Obermenge der gebotenen Funktionen der `private` Klausel. Die Syntax der `lastprivate` -Klausel ist wie folgt:  
  
```  
lastprivate(variable-list)  
```  
  
 Variablen in der *Variablenliste* haben `private` Klausel Semantik. Wenn eine `lastprivate` -Klausel wird angezeigt, auf die Richtlinie, die ein Konstrukt Freigeben von Arbeit, den Wert der einzelnen identifiziert `lastprivate` Variable aus der sequenziell letzten Iteration der Schleife zugeordnet, oder die lexikalisch letzten abschnittsdirektive, zugewiesen ist die Variablen des ursprünglichen Objekts. Variablen, die nicht die letzte Iteration der ein Wert zugewiesen der **für** oder **für parallele**, oder durch lexikalisch letzten Abschnitt der **Abschnitte** oder  **Parallel Sections-** Richtlinie haben unbestimmte Werte nach der Erstellung. Nicht zugewiesene Unterobjekte haben auch einen unbestimmten Wert nach dem Konstrukt.  
  
 Die Einschränkungen fest, die `lastprivate` Klausel lauten wie folgt:  
  
-   Alle Einschränkungen für `private` anwenden.  
  
-   Eine Variable mit einem Klassentyp sein, die als angegeben wird `lastprivate` benötigen eine erreichbare, eindeutige Kopierzuweisungsoperator.  
  
-   Variablen, die innerhalb eines parallelen Bereichs privaten sind bzw. die angezeigt werden, in, der `reduction` -Klausel der eine **parallele** Richtlinie kann nicht angegeben werden, eine `lastprivate` -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden.