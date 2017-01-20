---
title: "AsyncBase::Start-Methode"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::Start"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Start-Methode"
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
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