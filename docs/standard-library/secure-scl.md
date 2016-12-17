---
title: "_SECURE_SCL"
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
  - "_SECURE_SCL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SECURE_SCL"
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# _SECURE_SCL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert, dass [Überprüfte Iteratoren](../standard-library/checked-iterators.md) aktiviert werden.  Wenn es als 1 definiert wird, verursacht unsichere Iteratorverwendung einen Laufzeitfehler und das Programm wird beendet.  Wenn es als 0 definiert sind, werden feststellen Iteratoren deaktiviert.  Im Debugmodus ist der Standardwert für **\_SECURE\_SCL** 1 heißt, dass für Iteratoren aktiviert werden.  Im Releasemodus ist der Standardwert für `_SECURE_SCL` 0.  
  
> [!IMPORTANT]
>  mit `_ITERATOR_DEBUG_LEVEL`, `_SECURE_SCL` zu steuern.  Weitere Informationen finden Sie unter [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
## Hinweise  
 So aktivieren überprüfte Iteratoren, legen Sie **\_SECURE\_SCL** auf 1:  
  
```  
#define _SECURE_SCL 1  
```  
  
 Um zu deaktivieren überprüfte Iteratoren, legen Sie **\_SECURE\_SCL** auf 0:  
  
```  
#define _SECURE_SCL 0  
```  
  
 Informationen, wie Warnungen zu überprüfen Iteratoren, finden Sie unter [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## Siehe auch  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)   
 [Überprüfte Iteratoren](../standard-library/checked-iterators.md)   
 [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)   
 [Sichere Bibliotheken: C\+\+\-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)