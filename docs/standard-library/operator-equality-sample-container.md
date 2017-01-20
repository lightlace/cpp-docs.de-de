---
title: "operator== (&lt;sample container&gt;)"
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
  - "std.=="
  - "std::=="
  - "operator=="
  - "std.operator=="
  - "std::operator=="
  - "=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "==-Operator, mit spezifischen Standard-C++-Objekten"
  - "Operator ==, Container"
  - "Operator==, Container"
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
caps.latest.revision: 9
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# operator== (&lt;sample container&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dieses Thema ist in der Visual C\+\+\-Dokumentation nicht als funktionsfähiges Beispiel von den Containern, die in der C\+\+\-Standardbibliothek verwendet werden.  Weitere Informationen finden Sie unter [STL\-Container](../standard-library/stl-containers.md).  
  
 Überlädt `operator==`, um zwei Objekte Vorlagenklasse [Container](../standard-library/sample-container-class.md) vergleichen.  
  
## Syntax  
  
```  
  
   template<class Ty>  
bool operator==(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## Rückgabewert  
 Gibt `_Left`**.**[size](../standard-library/container-class-size.md) **\=\=** `_Right`**.size && equal**\(\_*Left***.**[begin](../standard-library/container-class-begin.md), `_Left` zurück.  [Ende](../standard-library/container-class-end.md)*, \_Right***.begin**\).  
  
## Siehe auch  
 [\<sample container\>](../standard-library/sample-container.md)