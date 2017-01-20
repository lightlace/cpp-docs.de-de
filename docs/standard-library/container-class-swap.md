---
title: "Container-Klasse::swap"
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
helpviewer_keywords: 
  - "swap-Methode"
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: 8
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Container-Klasse::swap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dieses Thema ist in der Visual C\+\+\-Dokumentation nicht als funktionsfähiges Beispiel von den Containern, die in der C\+\+\-Standardbibliothek verwendet werden.  Weitere Informationen finden Sie unter [STL\-Container](../standard-library/stl-containers.md).  
  
 Vertauscht die gesteuerten Sequenzen zwischen **\*this** und `_Right`.  
  
## Syntax  
  
```  
  
      void swap(  
   Container& _Right  
);  
```  
  
## Hinweise  
 Wenn  **get\_allocator \=\=** `_Right`**.get\_allocator**, es so in der konstanten Zeit ausführt.  Andernfalls führt einige Element\-Zuweisungen aus und Konstruktor ruft proportional zur Anzahl der Elemente in beiden Sequenzen gesteuerten auf.  
  
## Siehe auch  
 [Sample Container\-Klasse](../standard-library/sample-container-class.md)