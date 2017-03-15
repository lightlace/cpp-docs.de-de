---
title: "HandleT::HandleT-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HandleT, Konstruktor"
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HandleT::HandleT-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine neue Instanz der HandleT\-Klasse.  
  
## Syntax  
  
```  
explicit HandleT(  
   typename HandleTraits::Type h =   
      HandleTraits::GetInvalidValue()  
);  
  
HandleT(  
   _Inout_ HandleT&& h  
);  
```  
  
#### Parameter  
 `h`  
 Ein Handler.  
  
## Hinweise  
 Der erste Konstruktor initialisiert ein HandleT\-Objekt, kein gültiges Handle zu einem Objekt.  Der zweite Konstruktor erstellt ein neues HandleT\-Objekt vom Parameter `h`.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HandleT\-Klasse](../windows/handlet-class.md)