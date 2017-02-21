---
title: "ML Warning A4012 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A4012"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A4012"
ms.assetid: 842b1259-9679-4eeb-a02d-672a583a94e5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Warning A4012
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Zeilennummerninformationen für Segment ohne den CODE " Klasse“**  
  
 Es gab Anweisungen in einem Segment, das hat keinen CODE den Klassennamen endet mit „.“ Der Assembler generierte nicht CodeView\-Informationen für diese Anweisungen.  
  
 CodeView können Module mit Code in Segmenten mit dem Klassennamen nicht verarbeiten, die beendet werden CODE nicht mit „.“  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)