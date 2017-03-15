---
title: "EventTargetArray::AddTail-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::EventTargetArray::AddTail"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddTail-Methode"
ms.assetid: d0fafab9-049c-40e0-a40c-d126c9ee63e6
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# EventTargetArray::AddTail-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
void AddTail(  
   _In_ IUnknown* element  
);  
```  
  
#### Parameter  
 `element`  
 Zeiger zum Anfügen Ereignishandler.  
  
## Hinweise  
 Fügt den angegebenen Ereignishandler dem Ende des internen Arrays der Ereignishandler dargestellt.  
  
 AddTail\(\) soll, nur durch die EventSource\-Klasse intern verwendet werden.  
  
## Anforderungen  
 **Header:** event.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [EventTargetArray\-Klasse](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)