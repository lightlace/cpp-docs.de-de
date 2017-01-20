---
title: "2.7.2.2 firstprivate"
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
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.2 firstprivate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **firstprivate**\-Klausel stellt eine Obermenge der Funktionen, die von der **private**\-Klausel.  Die Syntax der **firstprivate**\-Klausel lautet wie folgt:  
  
```  
firstprivate(variable-list)  
```  
  
 Die Variablen, die *in der Liste Variable* angegeben werden **private** Semantik \- Klausel, wie in [2.7.2.1 Abschnitt](../../parallel/openmp/2-7-2-1-private.md) auf Seite 25 beschrieben.  Die Initialisierung oder der Konstruktion geschieht, als ob er einmal pro Thread vorgenommen wurde, bevor die Ausführung des Threads des Konstrukts.  Für eine **firstprivate**\-Klausel in einem parallelen Konstrukt, ist der Anfangswert des neuen privaten Objekts der Wert des ursprünglichen Objekts, das unmittelbar vor dem parallelen Konstrukt für den Thread vorhanden ist, der er stößt.  Für eine **firstprivate**\-Klausel in einem Arbeitsteilungs konstrukt, ist der Anfangswert des neuen privaten Objekts für jeden Thread, der ausgeführt wird, das Arbeitsteilungs konstrukt der Wert des ursprünglichen Objekts, das vor dem Zeitpunkt ist, dass derselbe Thread das Arbeitsteilungs konstrukt auftritt.  Außerdem für C\+\+\-Objekte, ist das neue private Objekt für jeden Thread die Kopie, die aus dem ursprünglichen Objekt erstellt wird.  
  
 Die Einschränkungen zur **firstprivate**\-Klausel lauten wie folgt:  
  
-   Eine Variable, die in einer **firstprivate**\-Klausel angegeben ist, darf einen unvollständigen Typ oder einen Verweistyp enthalten.  
  
-   Eine Variable mit einem Klassentyp, der angegeben wird, während **firstprivate** einen zugreifbaren, eindeutigen Kopierkonstruktor aufweisen muss.  
  
-   Variablen, die innerhalb eines parallelen Bereichs privat sind oder die in der **Verringerung**\-Klausel **Ähnlichkeit**\-Direktive angezeigt werden, können nicht in einer **firstprivate**\-Klausel auf Arbeitsteilungs direktiven angegeben werden, die zum parallelen Konstrukt bindet.