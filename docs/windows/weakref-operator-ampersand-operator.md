---
title: "WeakRef::operator&amp;-Operator"
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
  - "client/Microsoft::WRL::WeakRef::operator&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator&-Operator"
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# WeakRef::operator&amp;-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt einen ComPtrRef\-Objekt zurück, die das aktuelle WeakRef\-Objekt darstellt.  
  
## Syntax  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&() throw()  
```  
  
## Rückgabewert  
 Ein ComPtrRef\-Objekt, die das aktuelle WeakRef\-Objekt darstellt.  
  
## Hinweise  
 Dies ist ein interner Hilfeoperator, der nicht verwendet wird, im Code verwendet werden.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [WeakRef\-Klasse](../windows/weakref-class.md)