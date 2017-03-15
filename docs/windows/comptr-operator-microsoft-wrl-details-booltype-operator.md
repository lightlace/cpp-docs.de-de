---
title: "ComPtr::operator Microsoft::WRL::Details::BoolType-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
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