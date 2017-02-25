---
title: "vector&lt;bool&gt;::reference::operator bool | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
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