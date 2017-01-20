---
title: "2.4 Work-sharing Constructs"
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
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4 Work-sharing Constructs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Arbeitsteilungs konstrukt verteilt die Ausführung der zugeordneten Anweisung bei den Mitgliedern des Teams, die es feststellen.  Die Arbeitsteilungs Direktiven keine neuen Threads gestartet, und es gibt keine implizite Grenze ein Eintrag zu einem Arbeitsteilungs konstrukt.  
  
 Die Sequenz der den aufgetretenen Arbeitsteilungs konstrukten und muss mit **Barriere**\-Direktive für jeden Thread in einem Team sein.  
  
 OpenMP definiert die folgenden Arbeitsteilungs Programmierkonstrukte, und diese werden in den folgenden Abschnitten beschrieben:  
  
-   **nach**\-Direktive  
  
-   **Abschnitte**\-Direktive  
  
-   **Einfach**\-Direktive