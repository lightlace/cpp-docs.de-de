---
title: "2.7.2.7 copyin"
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
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.7 copyin
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **copyin**\-Klausel stellt einen Mechanismus bereit, um denselben Wert **threadprivate**\-Variablen für jeden Thread im Team zuweisen, das den parallelen Bereich ausgeführt wird.  Für jede Variable, die in einer **copyin**\-Klausel angegeben ist, wird der Wert der Variablen im Masterthread des Teams, als sei es durch Zuweisung, threadprivaten Kopien zu Beginn des parallelen Bereichs kopiert.  Die Syntax der **copyin**\-Klausel lautet wie folgt:  
  
```  
  
copyin(  
variable-list  
)  
  
```  
  
 Die Einschränkungen zur **copyin**\-Klausel lauten wie folgt:  
  
-   Eine Variable, die in der **copyin**\-Klausel angegeben wird, muss über einen zugreifbaren, eindeutigen Kopierzuweisungsoperator sein.  
  
-   Eine Variable, die in der **copyin**\-Klausel angegeben wird, muss eine **threadprivate**\-Variable sein.