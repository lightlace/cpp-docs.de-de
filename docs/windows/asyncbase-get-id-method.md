---
title: "AsyncBase::get_Id-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::get_Id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "get_Id-Methode"
ms.assetid: 591d8366-ea76-4deb-9278-9d3bc394a42b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::get_Id-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft das Handle des asynchronen Vorgangs ab.  
  
## Syntax  
  
```  
STDMETHOD(  
   get_Id  
)(unsigned int *id) override;  
```  
  
#### Parameter  
 `id`  
 Der Speicherort, an dem das Handle gespeichert werden soll.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls E\_ILLEGAL\_METHOD\_CALL.  
  
## Hinweise  
 Diese Methode implementiert IAsyncInfo::get\_Id.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)