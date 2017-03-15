---
title: "AsyncBase::ErrorCode-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::ErrorCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorCode-Methode"
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::ErrorCode-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.  
  
## Syntax  
  
```  
inline void ErrorCode(  
   HRESULT *error  
);  
```  
  
#### Parameter  
 `error`  
 Der Speicherort, in dem dieser Operation den aktuellen Fehlercode speichert.  
  
## Hinweise  
 Dieser Vorgang ist threadsicher.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)