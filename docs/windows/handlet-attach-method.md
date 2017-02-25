---
title: "HandleT::Attach-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach-Methode"
ms.assetid: a8783a18-bbf6-456c-98a3-e2048a10d79f
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HandleT::Attach-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ordnet das angegebene Handle mit dem aktuellen HandleT\-Objekt zu.  
  
## Syntax  
  
```  
void Attach(  
   typename HandleTraits::Type h  
);  
```  
  
#### Parameter  
 `h`  
 Ein Handler.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HandleT\-Klasse](../windows/handlet-class.md)