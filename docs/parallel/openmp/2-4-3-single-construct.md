---
title: "2.4.3 single Construct"
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
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.3 single Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **Einfach**\-Direktive identifizieren ein Konstrukt, das angibt, dass der entsprechende strukturierte Block mit nur einem Thread im Team ausgeführt wird \(nicht unbedingt der Masterthread\).  Die Syntax der **Einfach**\-Direktive sieht wie folgt aus:  
  
```  
#pragma omp single [clause[[,] clause] ...] new-line  
   structured-block  
```  
  
 Die Klausel ist eine der folgenden Aktionen aus:  
  
 **\(privat**Variable*Liste***\)**  
  
 **\(firstprivate**Variable*Liste***\)**  
  
 **\(copyprivate**Variable*Liste***\)**  
  
 **nowait**  
  
 Es gibt eine implizite Grenze nach dem **Einfach** Konstrukt, es sei denn, eine **nowait**\-Klausel angegeben wird.  
  
 Einschränkungen für **Einfach**\-Direktive lauten wie folgt:  
  
-   Nur eine einzige **nowait**\-Klausel kann auf **Einfach**\-Direktive angezeigt werden.  
  
-   Die copyprivat\-Klausel darf nicht mit der **nowait**\-Klausel verwendet werden.  
  
## Querverweise:  
  
-   **private**, **firstprivate**und copyprivat\-Klauseln finden [2.7.2 Abschnitt](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.