---
title: "AsyncBase::put_Id-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::put_Id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "put_Id-Methode"
ms.assetid: aebad85f-4774-42de-b625-a9cf5f65cb4e
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::put_Id-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt das Handle des asynchronen Vorgangs fest.  
  
## Syntax  
  
```  
STDMETHOD(  
   put_Id  
)(const unsigned int id);  
```  
  
#### Parameter  
 `id`  
 Ein Handle ungleich 0.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls E\_INVALIDARG oder E\_ILLEGAL\_METHOD\_CALL.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)