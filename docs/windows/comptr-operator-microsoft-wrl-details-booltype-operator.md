---
title: "ComPtr::operator Microsoft::WRL::Details::BoolType-Operator"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator Microsoft::WRL::Details::BoolType-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob ein ComPtr die Objektlebensdauer einer Schnittstelle verwaltet.  
  
## Syntax  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## Rückgabewert  
 Wenn eine Schnittstelle mit diesem ComPtr zugeordnet wird, die Adresse des [BoolStruct::Member](../windows/boolstruct-member-data-member.md) Datenmembers; andernfalls `nullptr`.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ComPtr\-Klasse](../windows/comptr-class.md)   
 [ComPtr::Get\-Methode](../windows/comptr-get-method.md)