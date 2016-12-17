---
title: "ML Nonfatal Error A2066"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "A2066"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2066"
ms.assetid: 58220fdf-fb8f-47fc-a36d-737867361185
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2066
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Größe des Segments und CPU\-Modus inkompatibel**  
  
 Es wurde versucht, ein Segment mit einem **USE16**, **USE32**oder **FLAT**\-Attribut zu öffnen, die nicht mit dem angegebenen CPU war, kompatibel oder ein 16\-Bit\- CPUs in einem 32\-Bit\-Segment während zu ändern.  
  
 Die **USE32** und **FLAT**\-Attribute müssen aus mindestens .386 aus den Prozessor direktiven vorangestellt werden.  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)