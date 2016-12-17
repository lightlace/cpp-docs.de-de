---
title: "2.9 Directive Nesting"
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
ms.assetid: 6565a43c-fd2d-4366-8322-8d75e1b06600
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# 2.9 Directive Nesting
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dynamische Schachtelung von Direktiven gehorchen muss die folgenden Regeln:  
  
-   **Ähnlichkeit**\-Direktive dynamisch in ein anderes Team ein neues logisches **Ähnlichkeit** legen fest, das nur vom aktuellen Thread zusammensetzt, es sei denn, geschachtelter Parallelität aktiviert ist.  
  
-   **nach**, **Abschnitte**und **Einfach**\-Direktive, die auf demselben **Ähnlichkeit** binden, werden nicht zulässig, ineinander geschachtelt werden soll.  
  
-   **Kritisch**\-Direktive mit demselben Namen sind nicht zulässig, ineinander geschachtelt werden soll.  Beachten Sie, dass diese Einschränkung ist nicht ausreichend, Deadlock zu verhindern.  
  
-   **nach**, **Abschnitte**und **Einfach**\-Direktiven sind nicht im dynamischen Wertebereich von **Kritisch**, **geordnet**und **Master** Bereichen wenn die Direktive an demselben **Ähnlichkeit** wie die Bereiche zulässig.  
  
-   **Barriere**\-Direktiven sind nicht im dynamischen Wertebereich von **nach**, **geordnet**, **Abschnitte**, **Einfach**, **Master**und **Kritisch** Bereichen wenn die Direktive verbindlich **Ähnlichkeit** gleichen sein wie die Bereiche zulässig.  
  
-   **Master**\-Direktiven sind nicht im dynamischen Wertebereich von **nach**, **Abschnitte**und **Einfach**\-Direktive wenn das **Master**\-Direktive verbindlich **Ähnlichkeit** gleichen sein wie die Arbeitsteilungs Direktiven zulässig.  
  
-   **geordnet**\-Direktiven sind nicht im dynamischen Wertebereich von **Kritisch** Bereichen wenn die Direktive verbindlich **Ähnlichkeit** gleichen sein wie die Bereiche zulässig.  
  
-   Alle Direktiven, die zulässig ist, wenn sie dynamisch in einem parallelen Bereichs ausgeführt werden, sind ebenfalls nicht zulässig, wenn sie außerhalb eines parallelen Bereichs ausgeführt werden.  Wenn sie dynamisch außerhalb eines vom Benutzer angegebenen parallelen Bereichs ausgeführt werden, werden die Direktive von einem Team ausgeführt, das nur aus dem Masterthread besteht.