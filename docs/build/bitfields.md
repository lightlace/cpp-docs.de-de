---
title: "Bitfelder | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bitfelder"
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Bitfelder
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Struktur\-Bitfelder sind auf 64 Bits begrenzt und können vom Typ "signed int", "unsigned int", "int64" oder "unsigned int64" sein.  Bei Bitfeldern, die die Typgrenze überschreiten, werden Bits übersprungen, damit das Bitfeld an der nächsten Typenausrichtung ausgerichtet werden kann.  Zum Beispiel dürfen integer\-Bitfelder eine 32\-Bit\-Grenze nicht überschreiten.  
  
## Siehe auch  
 [Typen und Speicher](../build/types-and-storage.md)