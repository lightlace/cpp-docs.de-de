---
title: "Event::operator=-Operator"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Event::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator=-Operator"
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# Event::operator=-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Weist den angegebenen Ereignisverweis der aktuellen Ereignisinstanz zu.  
  
## Syntax  
  
```  
WRL_NOTHROW Event& operator=(  
   _Inout_ Event&& h  
);  
```  
  
#### Parameter  
 `h`  
 Ein zu einer rvalu\-Verweis Ereignisinstanz.  
  
## Rückgabewert  
 Ein Zeiger auf Tagesereignisseinstanz.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Ereignisklasse \(C\+\+\-Vorlagenbibliothek der Windows\-Runtime\)](../windows/event-class-windows-runtime-cpp-template-library.md)