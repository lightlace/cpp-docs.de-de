---
title: "AsyncBase::Cancel-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::Cancel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Cancel-Methode"
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::Cancel-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bricht einen asynchronen Vorgang ab.  
  
## Syntax  
  
```  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## Rückgabewert  
 Standardmäßig gibt immer S\_OK zurück.  
  
## Hinweise  
 Cancel\(\) ist eine Standardimplementierung von IAsyncInfo::Cancel und beinhaltet keine eigentliche Arbeit.  Um einen asynchronen Operation tatsächlich abzubrechen, überschreiben Sie die reine virtuelle Methode OnCancel\(\).  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)