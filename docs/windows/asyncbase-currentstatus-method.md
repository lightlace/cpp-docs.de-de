---
title: "AsyncBase::CurrentStatus-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::CurrentStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CurrentStatus-Methode"
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::CurrentStatus-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den Status des aktuellen asynchronen Vorgangs ab.  
  
## Syntax  
  
```  
inline void CurrentStatus(  
   Details::AsyncStatusInternal *status  
);  
```  
  
#### Parameter  
 `status`  
 Der Speicherort, in dem dieser Operation den aktuellen Status speichert.  
  
## Hinweise  
 Dieser Vorgang ist threadsicher.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)   
 [AsyncStatusInternal\-Enumeration](../windows/asyncstatusinternal-enumeration.md)