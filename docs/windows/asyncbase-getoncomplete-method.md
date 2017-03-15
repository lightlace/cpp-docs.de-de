---
title: "AsyncBase::GetOnComplete-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::GetOnComplete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetOnComplete-Methode"
ms.assetid: f06ae02d-9a88-41d2-b749-bdc1a7ff8748
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::GetOnComplete-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Kopiert die Adresse des aktuellen Abschlussereignishandlers der angegebenen Variable.  
  
## Syntax  
  
```  
STDMETHOD(  
   GetOnComplete  
)(TComplete** completeHandler);  
```  
  
#### Parameter  
 `completeHandler`  
 Der Speicherort, in dem die jeweilige Adresse des aktuellen Abschlussereignishandlers gespeichert wird.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls E\_ILLEGAL\_METHOD\_CALL.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)