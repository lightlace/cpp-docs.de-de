---
title: "2.6.2 critical Construct"
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
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.2 critical Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **Kritisch**\-Direktive identifizieren ein Konstrukt, das die Ausführung des entsprechenden strukturierten Blocks zu einem einzigen Thread gleichzeitig einschränkt.  Die Syntax der **Kritisch**\-Direktive sieht wie folgt aus:  
  
```  
#pragma omp critical [(name)]  new-line  
   structured-block  
```  
  
 Ein optionaler *Name* kann verwendet werden, um den kritischen Abschnitt zu identifizieren.  Die Bezeichner, die verwendet werden, um einen kritischen Abschnitt zu identifizieren, verfügen über externe Bindung und befinden sich in einem Namespace, der getrennt von den Namespaces ist, die von den Bezeichnungen von Tagen, Member und den gewöhnlichen Bezeichnern verwendet werden.  
  
 Ein Thread wartet am Anfang eines kritischen Abschnitts, wenn kein anderer Thread einen kritischen Abschnitt \(eine beliebige Stelle im Programm\) mit dem gleichen Namen ausgeführt wird.  Alle unbenannte **Kritisch**\-Direktive auf denselben nicht angegeben Namen zugeordnet.