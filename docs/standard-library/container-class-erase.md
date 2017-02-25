---
title: "Container-Klasse::erase | Microsoft Docs"
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
helpviewer_keywords: 
  - "erase-Methode"
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Container-Klasse::erase
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dieses Thema ist in der Visual C\+\+\-Dokumentation nicht als funktionsfähiges Beispiel von den Containern, die in der C\+\+\-Standardbibliothek verwendet werden.  Weitere Informationen finden Sie unter [STL\-Container](../standard-library/stl-containers.md).  
  
 Löscht ein Element.  
  
## Syntax  
  
```  
  
      iterator erase(  
   iterator _Where   
);  
iterator erase(  
   iterator _First,  
   iterator _Last   
);  
```  
  
## Hinweise  
 Die erste Memberfunktion entfernt das Element der gesteuerten Sequenz, auf die von \_*Where* gezeigt wird**.** Die zweite Memberfunktion entfernt die Elemente der gesteuerten Sequenz im Bereich \[`_First`, `_Last`\).  Beides Rückgabe ein Iterator, der das erste Element festgelegt, das über allen Elementen entfernt hinaus bleibt oder [Ende](../standard-library/container-class-end.md), wenn kein solches Element vorhanden ist.  
  
 Die Memberfunktionen lösen eine Ausnahme aus, wenn ein Kopiervorgang eine Ausnahme auslöst.  
  
## Siehe auch  
 [Sample Container\-Klasse](../standard-library/sample-container-class.md)