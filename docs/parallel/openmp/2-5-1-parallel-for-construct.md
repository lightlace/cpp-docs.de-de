---
title: "2.5.1 parallel for Construct"
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
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# 2.5.1 parallel for Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **für Ähnlichkeit**\-Direktive ist eine Kurzform für einen **Ähnlichkeit** Bereich, der nur einzelne **nach**\-Direktive enthält.  Die Syntax der **für Ähnlichkeit**\-Direktive sieht wie folgt aus:  
  
```  
#pragma omp parallel for [clause[[,] clause] ...] new-line  
   for-loop  
```  
  
 Mit dieser Direktive können alle Klauseln der **Ähnlichkeit**\-Direktive und der **nach**\-Direktive, mit Ausnahme der `nowait`\-Klausel mit identischen Bedeutung und Einschränkungen.  Die Semantik ist mit **Ähnlichkeit**\-Direktive explizit angeben identisch, die sofort aus **nach**\-Direktive folgen.  
  
## Querverweise:  
  
-   **Ähnlichkeit**\-Direktive finden [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite 8.  
  
-   **nach**\-Direktive finden [2.4.1 Abschnitt](../../parallel/openmp/2-4-1-for-construct.md) auf Seite 11.  
  
-   Attribut für Daten klauseln finden [2.7.2 Data\-Sharing Attribute Clauses](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.