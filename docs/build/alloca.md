---
title: "alloca"
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
ms.assetid: 2b209335-e3a0-4934-93f0-3b5925d22918
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# alloca
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[\_alloca](../c-runtime-library/reference/alloca.md) muss auf 16 Byte ausgerichtet sein und einen Framezeiger verwenden.  
  
 Unterhalb des reservierten Stapels muss Speicherplatz für Parameter nachfolgend aufgerufener Funktionen mit berücksichtigt werden, wie unter [Stapelreservierung](../build/stack-allocation.md) erläutert wird.  
  
## Siehe auch  
 [Verwendung von Stapeln](../build/stack-usage.md)