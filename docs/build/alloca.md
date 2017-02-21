---
title: "alloca | Microsoft Docs"
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
ms.assetid: 2b209335-e3a0-4934-93f0-3b5925d22918
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# alloca
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[\_alloca](../c-runtime-library/reference/alloca.md) muss auf 16 Byte ausgerichtet sein und einen Framezeiger verwenden.  
  
 Unterhalb des reservierten Stapels muss Speicherplatz für Parameter nachfolgend aufgerufener Funktionen mit berücksichtigt werden, wie unter [Stapelreservierung](../build/stack-allocation.md) erläutert wird.  
  
## Siehe auch  
 [Verwendung von Stapeln](../build/stack-usage.md)