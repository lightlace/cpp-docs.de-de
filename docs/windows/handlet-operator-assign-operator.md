---
title: "HandleT::operator=-Operator"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator=-Operator"
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT::operator=-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verschiebt den Wert des angegebenen HandleT\-Objekts dem aktuellen HandleT\-Objekt.  
  
## Syntax  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### Parameter  
 `h`  
 Ein rvalu\-Verweis einem Handle.  
  
## Rückgabewert  
 Ein Verweis auf den aktuellen HandleT\-Objekt.  
  
## Hinweise  
 Dieser Vorgang macht das HandleT\-Objekt ungültig durch Parameter `h` angegeben wird.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HandleT\-Klasse](../windows/handlet-class.md)