---
title: "2.5.2 parallel sections Construct"
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
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 2.5.2 parallel sections Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **parallele Abschnitte**\-Direktive Verknüpfung erstellen ein Formular zum Angeben eines **Ähnlichkeit** Bereichs bereit, der nur einzelne **Abschnitte**\-Direktive enthält.  Die Semantik ist mit **Ähnlichkeit**\-Direktive explizit angeben identisch, die sofort aus **Abschnitte**\-Direktive folgen.  Die Syntax der **parallele Abschnitte**\-Direktive sieht wie folgt aus:  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-line  
      structured-block  ]  
   ...  
}  
```  
  
 Die *Klausel* kann eine der Klauseln sein, die von der **Ähnlichkeit** und **Abschnitte**\-Direktive, mit Ausnahme der **nowait**\-Klausel akzeptiert werden.  
  
## Querverweise:  
  
-   **Ähnlichkeit**\-Direktive finden [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite 8.  
  
-   **Abschnitte**\-Direktive finden [2.4.2 Abschnitt](../../parallel/openmp/2-4-2-sections-construct.md) auf Seite 14.