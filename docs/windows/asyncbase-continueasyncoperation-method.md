---
title: "AsyncBase::ContinueAsyncOperation-Methode"
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
  - "async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ContinueAsyncOperation-Methode"
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::ContinueAsyncOperation-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob die asynchrone Operation mit der Verarbeitung fortzufahren sollte oder sollte enthalten.  
  
## Syntax  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## Rückgabewert  
 `true`, wenn der aktuelle Status des asynchronen Vorgangs *started* ist, der den Vorgang bedeutet, sollten weiter ausgeführt.  Andernfalls sollte `false`, der den Vorgang bedeutet, angehalten.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)