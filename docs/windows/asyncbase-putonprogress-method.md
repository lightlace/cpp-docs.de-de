---
title: "AsyncBase::PutOnProgress-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::PutOnProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PutOnProgress-Methode"
ms.assetid: 1f5f180e-eb5a-4afe-ac16-69dbf36f0383
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::PutOnProgress-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt die Adresse des Statusereignishandlers auf den angegebenen Wert festgelegt.  
  
## Syntax  
  
```  
STDMETHOD(  
   PutOnProgress  
)(TProgress* progressHandler);  
```  
  
#### Parameter  
 `progressHandler`  
 Die Adresse, auf der der Statusereignishandler festgelegt wird.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls E\_ILLEGAL\_METHOD\_CALL.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)