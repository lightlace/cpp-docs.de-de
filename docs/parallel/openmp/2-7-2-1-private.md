---
title: "2.7.2.1 private"
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
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.1 private
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `private`\-Klausel deklariert die Variablen in der Liste Variablen zu jedem Thread in einem Team privat sein.  Die Syntax der `private`\-Klausel lautet wie folgt:  
  
```  
private(variable-list)  
```  
  
 Das Verhalten einer Variablen, die in einer `private`\-Klausel angegeben ist, lautet wie folgt.  Ein neues Objekt mit automatischer Speicherung dauer wird für das Konstrukt zugeordnet.  Die Größe und die Ausrichtung des neuen Objekts wird durch den Typ der Variablen bestimmt.  Diese Zuordnung tritt einmal für jeden Thread im Team behoben, und ein Standardkonstruktor für ein Klassenobjekt bei Bedarf aufgerufen. andernfalls ist der Anfangswert unbestimmt.  Das ursprüngliche Objekt, das durch die Variable verwiesen wird, können einen unbestimmten Wert nach Eintrag in das Konstrukt, Darf nicht innerhalb des Wertebereichs dynamischen Ändern des Konstrukts und weist einen unbestimmten Wert nach Beendigung des Konstrukts.  
  
 Im lexikalischen Wertebereich des Direktivenprozessors Konstrukts, wird die Variable mit dem neuen privaten Objekt, das von dem Thread zugeordnet ist.  
  
 Die Einschränkungen zur `private`\-Klausel lauten wie folgt:  
  
-   Eine Variable mit einem Klassentyp, der in einer `private`\-Klausel angegeben wird, muss über einen zugreifbaren, eindeutigen Standardkonstruktor verfügen.  
  
-   Eine Variable, die in einer `private`\-Klausel angegeben ist, darf **const**\- qualifizierten Typ nicht zulässig, es sei denn, sie einen Klassentyp mit einem `mutable`\-Member.  
  
-   Eine Variable, die in einer `private`\-Klausel angegeben ist, darf einen unvollständigen Typ oder einen Verweistyp enthalten.  
  
-   Variablen, die in der `reduction`\-Klausel **Ähnlichkeit**\-Direktive angezeigt werden, können nicht in einer `private`\-Klausel auf Arbeitsteilungs direktiven angegeben werden, die zum parallelen Konstrukt bindet.