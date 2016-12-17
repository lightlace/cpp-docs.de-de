---
title: "vector&lt;bool&gt;::reference::operator bool"
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
  - "operatorbool"
  - "vector<bool>::reference::operatorbool"
  - "bool"
  - "std::vector<bool>::reference::operatorbool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BOOL-Operator"
  - "reference::operator bool"
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
caps.latest.revision: 20
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# vector&lt;bool&gt;::reference::operator bool
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine implizite Konvertierung von `vector<bool>::reference` in `bool` bereit.  
  
## Syntax  
  
```  
operator bool( ) const;  
```  
  
## Rückgabewert  
 Der boolesche Wert des Elements des [vector \<bool\>](../standard-library/vector-bool-class.md)\-Objekts.  
  
## Hinweise  
 Das `vector<bool>`\-Objekt kann von diesem Operator nicht geändert werden.  
  
## Anforderungen  
 **Header:** \<vector\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [vector\<bool\>::reference\-Klasse](../standard-library/vector-bool-reference-class.md)   
 [Standard Template Library](../misc/standard-template-library.md)