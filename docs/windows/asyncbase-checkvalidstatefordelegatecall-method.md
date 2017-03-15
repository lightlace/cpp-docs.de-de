---
title: "AsyncBase::CheckValidStateForDelegateCall-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CheckValidStateForDelegateCall-Methode"
ms.assetid: d997ebe7-2378-4e74-a379-f0f85e6922f0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::CheckValidStateForDelegateCall-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob Delegateigenschaften im aktuellen asynchronen Zustand geändert werden können.  
  
## Syntax  
  
```  
inline HRESULT CheckValidStateForDelegateCall();  
```  
  
## Rückgabewert  
 S\_OK, wenn Delegateigenschaften geändert werden können; andernfalls E\_ILLEGAL\_METHOD\_CALL.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)