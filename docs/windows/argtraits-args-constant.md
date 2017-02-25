---
title: "ArgTraits::args-Konstante | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::ArgTraits::args"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "args-Konstante"
ms.assetid: a68100ab-254b-4571-a0bc-946f1633a46b
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ArgTraits::args-Konstante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
static const int args = -1; ;  
```  
  
## Hinweise  
 Hält die Anzahl der Parameter auf der Aufrufmethode einer Delegatschnittstelle.  
  
## Hinweise  
 Wenn `args` entspricht, gibt \-1 kann keine Übereinstimmung für die Aufrufsmethodensignatur vorhanden sein an.  
  
## Anforderungen  
 **Header:** event.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [ArgTraits\-Struktur](../windows/argtraits-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)