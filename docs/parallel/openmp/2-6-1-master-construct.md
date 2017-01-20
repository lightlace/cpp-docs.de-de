---
title: "2.6.1 master Construct"
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
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.1 master Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **Master**\-Direktive identifizieren ein Konstrukt, das einen strukturierten Block angibt, der vom Masterthread des Teams ausgeführt wird.  Die Syntax der **Master**\-Direktive sieht wie folgt aus:  
  
```  
#pragma omp master new-line  
   structured-block  
```  
  
 Andere Threads im Team den nicht strukturierten zugeordneten Block übergeben.  Es gibt keine implizite Grenze entweder ein Eintrag aus dem Beenden oder Vorlagen konstrukt.