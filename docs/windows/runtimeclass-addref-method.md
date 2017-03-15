---
title: "RuntimeClass::AddRef-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::AddRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef-Methode"
ms.assetid: 9c705749-680b-4308-bbec-5b601e8e7dbd
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClass::AddRef-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Inkrementiert den Verweiszähler für das aktuelle RuntimeClass\-Objekt.  
  
## Syntax  
  
```  
STDMETHOD_(  
   ULONG,  
   AddRef  
)();  
```  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [RuntimeClass\-Klasse](../windows/runtimeclass-class.md)