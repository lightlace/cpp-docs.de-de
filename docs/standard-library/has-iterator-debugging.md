---
title: "_HAS_ITERATOR_DEBUGGING"
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
  - "_HAS_ITERATOR_DEBUGGING"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_HAS_ITERATOR_DEBUGGING"
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
caps.latest.revision: 7
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# _HAS_ITERATOR_DEBUGGING
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert, ob die Iteratordebuggingsfunktion in einem Debugbuild aktiviert ist.  Standardmäßig wird Iteratordebugging aktiviert.  Weitere Informationen finden Sie unter [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md).  
  
> [!IMPORTANT]
>  mit `_ITERATOR_DEBUG_LEVEL`, `_HAS_ITERATOR_DEBUGGING` zu steuern.  Weitere Informationen finden Sie unter [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
## Hinweise  
 Um Iteratordebugging in Debugbuilds zu aktivieren, legen Sie **\_HAS\_ITERATOR\_DEBUGGING** auf 1 fest:  
  
```  
#define _HAS_ITERATOR_DEBUGGING 1  
```  
  
 **\_HAS\_ITERATOR\_DEBUGGING** kann nicht bis 1 in Verkaufsversionen festgelegt werden.  
  
 Um Iteratordebugging in Debugbuilds zu deaktivieren, legen Sie **\_HAS\_ITERATOR\_DEBUGGING** auf 0 fest:  
  
```  
#define _HAS_ITERATOR_DEBUGGING 0  
```  
  
## Siehe auch  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)   
 [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)   
 [Überprüfte Iteratoren](../standard-library/checked-iterators.md)   
 [Sichere Bibliotheken: C\+\+\-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)