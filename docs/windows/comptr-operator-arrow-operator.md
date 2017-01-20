---
title: "ComPtr::operator-&gt;-Operator"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator->-Operator"
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator-&gt;-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben wird.  
  
## Syntax  
  
```  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## Rückgabewert  
 Zeiger auf den Typ angegeben durch den aktuellen Vorlagentypnamen.  
  
## Hinweise  
 Mit dieser Helferfunktion entfernt den Aufwand, der mit dem STDMETHOD\-Makro verursacht wird, verwendet.  Diese Funktion macht IUnknown\-Typen privat anstelle virtuellen.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ComPtr\-Klasse](../windows/comptr-class.md)