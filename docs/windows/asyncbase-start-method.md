---
title: "AsyncBase::Start-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::Start"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Start-Methode"
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::Start-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Startet den asynchronen Vorgang.  
  
## Syntax  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## Rückgabewert  
 S\_OK wenn die Vorgangsanfänge oder bereits gestartet wird; andernfalls E\_ILLEGAL\_STATE\_CHANGE.  
  
## Hinweise  
 Start\(\) ist eine Standardimplementierung von IAsyncInfo::Start und beinhaltet keine eigentliche Arbeit.  Um einen asynchronen Operation tatsächlich zu beginnen, überschreiben Sie die reine virtuelle Methode OnStart\(\).  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)