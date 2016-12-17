---
title: "2.6.6 ordered Construct"
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
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.6 ordered Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der strukturierte Block, welche **geordnet**\-Direktive erfolgreich ist, werden in der Reihenfolge ausgeführt, in der Iterationen in einer sequenziellen Schleife ausgeführt würden.  Die Syntax der **geordnet**\-Direktive sieht wie folgt aus:  
  
```  
#pragma omp ordered new-line  
   structured-block  
```  
  
 **geordnet**\-Direktive muss innerhalb des dynamischen **nach** eines Wertebereichs oder **für Ähnlichkeit** Konstrukts sein.  Die **nach** oder **für Ähnlichkeit**\-Direktive, in denen das **geordnet** Konstrukt bindet, müssen eine **geordnet**\-Klausel verfügen, die angegeben wird, wie in [2.4.1 Abschnitt](../../parallel/openmp/2-4-1-for-construct.md) auf Seite 11 beschrieben.  Bei der Ausführung eines **nach** oder **für Ähnlichkeit** \- Konstrukt mit einer **geordnet**\-Klausel werden **geordnet** Konstrukte ausschließlich in der Reihenfolge ausgeführt, in der sie in einer sequenziellen Ausführung der Schleife ausgeführt würden.  
  
 Einschränkungen für **geordnet**\-Direktive lauten wie folgt:  
  
-   Eine Iteration einer Schleife mit einem **nach** Konstrukt darf die gleichen Rang Direktive nicht mehrmals ausführen, und sie dürfen nicht mehr als eine **geordnet**\-Direktive ausführen.