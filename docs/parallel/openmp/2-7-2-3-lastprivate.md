---
title: 2.7.2.3 Lastprivate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d4b6c904766699c2cccdd129f32461a5d612113d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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