---
title: "&lt;typeindex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<typeindex>"
dev_langs: 
  - "C++"
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# &lt;typeindex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließen Sie das typeindex Standardheader \<ein, um\> eine Klasse zu definieren und zu funktionieren, das die Indizierung von Objekten der Klasse [type\_information](../cpp/type-info-class.md) unterstützen.  
  
## Syntax  
  
```cpp  
#include <typeindex>  
```  
  
## Hinweise  
 [hash\-Struktur](../standard-library/hash-structure.md) definiert `hash function`, das zum Zuordnen von Werten des Typs [type\_index](../standard-library/type-index-class.md) einer Verteilung von Indexwerten geeignet ist.  
  
 Die `type_index`\-Klasse umschließt einen Zeiger auf ein `type_info`\-Objekt der Vorlage in der Indizierung ein.  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)