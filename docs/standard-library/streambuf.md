---
title: "&lt; Streambuf &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<streambuf>"
  - "<streambuf>"
  - "streambuf/std::<streambuf>"
  - "std.<streambuf>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "streambuf-Header"
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# &lt; Streambuf &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügen Sie den iostreams\-Standardheader \<streambuf\> ein, um die Vorlagenklasse [basic\_streambuf](../standard-library/basic-streambuf-class.md) zu definieren, die die Basis für die Verwendung der iostreams\-Klassen ist. Dieser Header wird in der Regel von einem der anderen iostreams\-Header für Sie eingefügt. Sie müssen ihn nur selten direkt einfügen.  
  
## Syntax  
  
```  
  
#include <streambuf>  
  
```  
  
### TypeDefs  
  
|||  
|-|-|  
|[streambuf](../Topic/streambuf.md)|Eine Spezialisierung von `basic_streambuf`, die `char` als Vorlagenparameter verwendet.|  
|[wstreambuf](../Topic/wstreambuf.md)|Eine Spezialisierung von `basic_streambuf`, die `wchar_t` als Vorlagenparameter verwendet.|  
  
### Klassen  
  
|||  
|-|-|  
|[basic\_streambuf\-Klasse](assetId:///d9c706ba-ce01-43e0-b0b2-a558fc53ea8d)|Die Vorlagenklasse beschreibt eine abstrakte Basisklasse für die Ableitung eines Streampuffers, der die Übertragung von Elementen in eine und aus einer bestimmten Darstellung eines Streams steuert.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)