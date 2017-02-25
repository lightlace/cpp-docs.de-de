---
title: "Container-Klasse::rend | Microsoft Docs"
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
  - "rend-Methode"
ms.assetid: 80f3dd04-dd2c-4b52-b0ed-d567ec5d186c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Container-Klasse::rend
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dieses Thema ist in der Visual C\+\+\-Dokumentation nicht als funktionsfähiges Beispiel von den Containern, die in der C\+\+\-Standardbibliothek verwendet werden.  Weitere Informationen finden Sie unter [STL\-Container](../standard-library/stl-containers.md).  
  
 Die Memberfunktion gibt einem umgekehrten Iterator, der beim ersten Element der Sequenz zeigt \(oder direkt über dem Ende eine leere Sequenz hinaus\) zurück und legt das Ende der Rücksequenz fest.  
  
## Syntax  
  
```  
  
      const_reverse_iterator rend( ) const;   
reverse_iterator rend( );  
```  
  
## Siehe auch  
 [Sample Container\-Klasse](../standard-library/sample-container-class.md)