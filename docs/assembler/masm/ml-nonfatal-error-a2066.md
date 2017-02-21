---
title: "ML Nonfatal Error A2066 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2066"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2066"
ms.assetid: 58220fdf-fb8f-47fc-a36d-737867361185
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2066
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Größe des Segments und CPU\-Modus inkompatibel**  
  
 Es wurde versucht, ein Segment mit einem **USE16**, **USE32**oder **FLAT**\-Attribut zu öffnen, die nicht mit dem angegebenen CPU war, kompatibel oder ein 16\-Bit\- CPUs in einem 32\-Bit\-Segment während zu ändern.  
  
 Die **USE32** und **FLAT**\-Attribute müssen aus mindestens .386 aus den Prozessor direktiven vorangestellt werden.  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)