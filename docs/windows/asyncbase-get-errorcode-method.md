---
title: "AsyncBase::get_ErrorCode-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::get_ErrorCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "get_error_code-Methode"
ms.assetid: 50b4f8a2-9a21-4ea0-bb5d-7ff524d62aea
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::get_ErrorCode-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.  
  
## Syntax  
  
```  
STDMETHOD(  
   get_ErrorCode  
)(HRESULT* errorCode) override;  
```  
  
#### Parameter  
 `errorCode`  
 Der Speicherort, in dem der aktuelle Fehlercode gespeichert wird.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls E\_ILLEGAL\_METHOD\_CALL, wenn der aktuelle asynchrone Vorgang geschlossen wird.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)