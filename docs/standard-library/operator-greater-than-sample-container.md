---
title: "operator&gt; (&lt;sample container&gt;)"
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
  - "std::operator>"
  - "std.>"
  - "std.operator>"
  - "operator>"
  - "std::>"
  - ">"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ">-Operator, Vergleichen von spezifischen Objekten"
  - "Operator >"
ms.assetid: 49bd417a-3305-4ffa-9884-39d3904ed87d
caps.latest.revision: 9
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# operator&gt; (&lt;sample container&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dieses Thema ist in der Visual C\+\+\-Dokumentation nicht als funktionsfähiges Beispiel von den Containern, die in der C\+\+\-Standardbibliothek verwendet werden.  Weitere Informationen finden Sie unter [STL\-Container](../standard-library/stl-containers.md).  
  
 Überlädt **Operator \>**, um zwei Objekte Vorlagenklasse [Container](../standard-library/sample-container-class.md) vergleichen.  
  
## Syntax  
  
```  
  
   template<class Ty>  
bool operator*gt;(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## Rückgabewert  
 Gibt \_Right \< \_Left zurück.  
  
## Siehe auch  
 [\<sample container\>](../standard-library/sample-container.md)