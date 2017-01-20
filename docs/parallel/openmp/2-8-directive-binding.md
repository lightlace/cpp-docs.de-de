---
title: "2.8 Directive Binding"
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
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# 2.8 Directive Binding
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dynamische Bindung von Direktiven gehorchen muss die folgenden Regeln:  
  
-   Bindung **nach**, der **Abschnitte**, **Einfach**, **Master**und **Barriere**\-Direktive auf **Ähnlichkeit**einschließenden dynamisch, falls vorhanden, unabhängig vom Wert einer **If** FROM\-Klausel, die sich auf diese Direktive vorhanden ist.  Wenn kein paralleler Bereich gerade ausgeführt wird, werden die Direktive von einem Team ausgeführt, das nur aus dem Masterthread besteht.  
  
-   Die **geordnet**\-Direktive ist verbindlich **nach**einschließenden dynamisch zu.  
  
-   Die **atomar**\-Direktive erzwingen exklusiven Zugriff in Bezug auf **atomar**\-Direktive in allen Threads und nicht nur das aktuelle Team.  
  
-   Die **Kritisch**\-Direktive erzwingen exklusiven Zugriff in Bezug auf **Kritisch**\-Direktive in allen Threads und nicht nur das aktuelle Team.  
  
-   \- Direktive kann nicht auf allen \- Direktive außerhalb nächsten **Ähnlichkeit**verbindlich einschließenden dynamisch sein.