---
title: "2.7.2.3 lastprivate"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.3 lastprivate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `lastprivate`\-Klausel stellt eine Obermenge der Funktionen, die von der `private`\-Klausel.  Die Syntax der `lastprivate`\-Klausel lautet wie folgt:  
  
```  
lastprivate(variable-list)  
```  
  
 Die Variablen, die in der *Liste Variable* angegeben werden `private`\-Klausel enthalten ist.  Wenn eine `lastprivate`\-Klausel in der Direktive wird, die ein Arbeitsteilungs konstrukt, den Wert einer Variable aus der `lastprivate` sequenziell letzten Iteration der Schleife zugeordneten Direktiven oder die lexikalisch letzten Abschnitt wird an das ursprüngliche Objekt identifiziert, der der Variablen zugewiesen.  Variablen, die keinen Wert durch die letzte Iteration **nach** oder des **für Ähnlichkeit**lexikalisch oder über den letzten Abschnitt der **Abschnitte** oder **parallele Abschnitte**\-Direktive zugewiesen sind, können unbestimmte Werte nach dem Konstrukt.  Nicht zugewiesen Unterobjekte verfügen auch über einen unbestimmten Wert nach dem Konstrukt.  
  
 Die Einschränkungen zur `lastprivate`\-Klausel lauten wie folgt:  
  
-   Alle Einschränkungen gelten für `private` .  
  
-   Eine Variable mit einem Klassentyp, der angegeben wird, während `lastprivate` einen zugreifbaren, eindeutigen Kopierzuweisungsoperator sein muss.  
  
-   Variablen, die innerhalb eines parallelen Bereichs privat sind oder die in der `reduction`\-Klausel **Ähnlichkeit**\-Direktive angezeigt werden, können nicht in einer `lastprivate`\-Klausel auf Arbeitsteilungs direktiven angegeben werden, die zum parallelen Konstrukt bindet.