---
title: "ML Warning A4012"
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
  - "A4012"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A4012"
ms.assetid: 842b1259-9679-4eeb-a02d-672a583a94e5
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# ML Warning A4012
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Zeilennummerninformationen für Segment ohne den CODE " Klasse“**  
  
 Es gab Anweisungen in einem Segment, das hat keinen CODE den Klassennamen endet mit „.“ Der Assembler generierte nicht CodeView\-Informationen für diese Anweisungen.  
  
 CodeView können Module mit Code in Segmenten mit dem Klassennamen nicht verarbeiten, die beendet werden CODE nicht mit „.“  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)