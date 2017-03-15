---
title: "AsyncBase::PutOnComplete-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::PutOnComplete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PutOnComplete-Methode"
ms.assetid: 1c469ff9-b2df-4637-bf05-01a617043149
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::PutOnComplete-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt die Adresse des Abschlussereignishandlers auf den angegebenen Wert festgelegt.  
  
## Syntax  
  
```  
STDMETHOD(  
   PutOnComplete  
)(TComplete* completeHandler);  
```  
  
#### Parameter  
 `completeHandler`  
 Die Adresse, auf der der Abschlussereignishandler festgelegt wird.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls E\_ILLEGAL\_METHOD\_CALL.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)