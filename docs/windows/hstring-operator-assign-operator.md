---
title: "HString::Operator=-Operator"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator="
dev_langs: 
  - "C++"
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Operator=-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verschiebt den Wert eines anderen HString\-Objekts zum aktuellen HString\-Objekt.  
  
## Syntax  
  
```cpp  
HString& operator=(HString&& other) throw()  
```  
  
#### Parameter  
 `other`  
 Ein vorhandenes HString\-Objekt.  
  
## Hinweise  
 Der Wert des Objekts vorhandenen `other` wird dem aktuellen HString\-Objekt kopiert, und `other` wird das Objekt zerstört.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HString\-Klasse](../windows/hstring-class.md)