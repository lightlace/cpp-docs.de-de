---
title: "_WAIT_CHILD, _WAIT_GRANDCHILD | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_WAIT_GRANDCHILD"
  - "WAIT_CHILD"
  - "WAIT_GRANDCHILD"
  - "_WAIT_CHILD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_WAIT_CHILD-Konstante"
  - "_WAIT_GRANDCHILD-Konstante"
  - "WAIT_CHILD-Konstante"
  - "WAIT_GRANDCHILD-Konstante"
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _WAIT_CHILD, _WAIT_GRANDCHILD
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <process.h>  
  
```  
  
## Hinweise  
 Die `_cwait`\-Funktion kann von jedem Prozess verwendet werden, um auf einen anderen Prozess zu warten \(wenn die Prozess\-ID bekannt\).  Das Aktionsargument kann einer der folgenden Werte sein:  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`_WAIT_CHILD`|Aufrufen von Prozess\-Wartevorgänge bis angegebenen neuen Prozess beendet wird.|  
|`_WAIT_GRANDCHILD`|Aufrufen von Prozess wartet bis angegebenen neuen Prozess, und alle Prozesse, die von diesen neuen Prozess erstellt werden, beendet werden.|  
  
## Siehe auch  
 [\_cwait](../c-runtime-library/reference/cwait.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)