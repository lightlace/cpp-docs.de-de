---
title: "&lt;ccomplex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<ccomplex>"
dev_langs: 
  - "C++"
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# &lt;ccomplex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließt den STL\-Header [\<complex\>](../standard-library/complex.md) ein, der effektiv den Standard\-C\-Bibliotheksheader \<complex.h\> einschließt und die verknüpften Namen zum `std`\-Namespace hinzufügt.  
  
## Syntax  
  
```cpp  
  
#include <ccomplex>  
  
```  
  
## Hinweise  
 Durch Einschließen dieses Headers wird sichergestellt, dass die mit externer Bindung im Standard\-C\-Bibliotheksheader deklarierten Namen im `std`\-Namespace deklariert werden.  
  
 Der Name `clog`, der in \<complex.h\> deklariert wird, ist im `std`\-Namespace aufgrund potentieller Konflikte mit dem `clog`, das in [\<iostream\>](../standard-library/iostream.md) deklariert ist, nicht definiert.  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [STL\-Übersicht](../standard-library/cpp-standard-library-overview.md)