---
title: "Unterlauf von Gleitkommawerten"
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
  - "C"
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Unterlauf von Gleitkommawerten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.5.1** Ob die mathematischen Funktionen den ganzzahligen Ausdruck `errno` bei Unterlaufbereichsfehlern auf den Wert des `ERANGE`\-Makros festlegen  
  
 Ein Gleitkommaunterlauf legt den Ausdruck `errno` nicht auf `ERANGE` fest.  Wenn ein Wert nahe 0 \(Null\) ist und schließlich ein Unterlauf stattfindet, wird der Wert auf 0 \(Null\) festgelegt.  
  
## Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)