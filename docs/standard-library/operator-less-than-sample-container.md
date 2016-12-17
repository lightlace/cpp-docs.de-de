---
title: "operator&lt; (&lt;sample container&gt;)"
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
  - "std::operator<"
  - "operator<"
  - "std.<"
  - "<"
  - "std.operator<"
  - "std::<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<-Operator"
  - "<-Operator, Vergleichen von spezifischen Objekten"
  - "Operator <, valarrays"
  - "Operator<, valarrays"
ms.assetid: 31027dd6-53be-428b-b950-1dcb25393597
caps.latest.revision: 8
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# operator&lt; (&lt;sample container&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dieses Thema ist in der Visual C\+\+\-Dokumentation nicht als funktionsfähiges Beispiel von den Containern, die in der C\+\+\-Standardbibliothek verwendet werden.  Weitere Informationen finden Sie unter [STL\-Container](../standard-library/stl-containers.md).  
  
 Überlädt **Operator \<**, um zwei Objekte Vorlagenklasse [Container](../standard-library/sample-container-class.md) vergleichen.  
  
## Syntax  
  
```  
  
   template<class Ty>  
bool operator<(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## Rückgabewert  
 Gibt `lexicographical_compare` zurück \(\_Left.  [Starten](../standard-library/container-class-begin.md), \_Left.  [Ende](../standard-library/container-class-end.md), \_Right **.begin**, \_Right.**end**\).  
  
## Siehe auch  
 [\<sample container\>](../standard-library/sample-container.md)