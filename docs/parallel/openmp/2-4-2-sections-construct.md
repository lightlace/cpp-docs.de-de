---
title: "2.4.2 sections Construct"
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
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.2 sections Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **Abschnitte**\-Direktive identifizieren ein einfaches Arbeitsteilungs konstrukt, das einen Satz von Konstrukten angibt, die unter Threads in einem Team unterteilt werden sollen.  Jeder Abschnitt wird einmal durch einen Thread im Team ausgeführt.  Die Syntax der **Abschnitte**\-Direktive sieht wie folgt aus:  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-line  
      structured-block ]  
...  
}  
```  
  
 Die Klausel ist eine der folgenden Aktionen aus:  
  
 **\(privat**Variable*Liste***\)**  
  
 **\(firstprivate**Variable*Liste***\)**  
  
 **\(lastprivate**Variable*Liste***\)**  
  
 *Operator* **\(Verringerung :**  *Variable Liste* **\)**  
  
 **nowait**  
  
 Jeder Abschnitt wird von **Abschnitt**\-Direktive vorangestellt, obwohl die **Abschnitt**\-Direktive für den ersten Abschnitt optional sind.  Die **Abschnitt**\-Direktive muss innerhalb des lexikalischen Wertebereichs der **Abschnitte**\-Direktive angezeigt werden.  Es gibt eine implizite Grenze am Ende eines **Abschnitte** Konstrukts, es sei denn, **nowait** angegeben wird.  
  
 Einschränkungen für **Abschnitte**\-Direktive lauten wie folgt:  
  
-   **Abschnitt**\-Direktive darf nicht außerhalb des lexikalischen Wertebereichs der **Abschnitte**\-Direktive angezeigt werden.  
  
-   Nur eine einzige **nowait**\-Klausel kann auf **Abschnitte**\-Direktive angezeigt werden.  
  
## Querverweise:  
  
-   **private**, **firstprivate**, **lastprivate**und **Verringerung**\-Klauseln finden [2.7.2 Abschnitt](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.