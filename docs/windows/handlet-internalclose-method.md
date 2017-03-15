---
title: "HandleT::InternalClose-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InternalClose-Methode"
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HandleT::InternalClose-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließt das aktuelle HandleT\-Objekt.  
  
## Syntax  
  
```  
virtual bool InternalClose();  
```  
  
## Rückgabewert  
 `true`, wenn das aktuelle HandleT erfolgreich abgeschlossenen; andernfalls `false`.  
  
## Hinweise  
 InternalClose\(\) ist geschützt.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HandleT\-Klasse](../windows/handlet-class.md)