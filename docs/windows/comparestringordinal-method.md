---
title: "CompareStringOrdinal-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal"
dev_langs: 
  - "C++"
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# CompareStringOrdinal-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```cpp  
  
inline INT32 CompareStringOrdinal(  
   HSTRING lhs,   
   HSTRING rhs)  
```  
  
#### Parameter  
 `lhs`  
 Das erste HSTRING zu vergleichen.  
  
 `rhs`  
 Das zweite HSTRING zu vergleichen.  
  
## Rückgabewert  
  
|Wert|Bedingung|  
|----------|---------------|  
|\-1|`lhs` ist kleiner als `rhs`.|  
|0|`lhs` ist gleich `rhs`.|  
|1|`lhs` ist größer als `rhs`.|  
  
## Hinweise  
 Vergleicht zwei angegebenen HSTRING\-Objekte und gibt eine ganze Zahl zurück, die ihrer relativen Position in einer Sortierreihenfolge angibt.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::Details  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers::Details\-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)