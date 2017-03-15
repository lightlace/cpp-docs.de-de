---
title: "AsyncBase::TryTransitionToCompleted-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryTransitionToCompleted-Methode"
ms.assetid: 8d038e0a-47ec-4cfc-8aeb-6821282df67a
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::TryTransitionToCompleted-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob der aktuelle asynchrone Operation abgeschlossen wurde.  
  
## Syntax  
  
```  
bool TryTransitionToCompleted(  
   void  
);  
```  
  
## Rückgabewert  
 `true`, wenn die asynchrone Operation abgeschlossen wurde; andernfalls `false`.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)