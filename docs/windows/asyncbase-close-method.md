---
title: "AsyncBase::Close-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close-Methode"
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::Close-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließt den asynchronen Vorgang.  
  
## Syntax  
  
```  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## Rückgabewert  
 S\_OK, wenn der Vorgang beendet oder bereits geschlossen wird; andernfalls E\_ILLEGAL\_STATE\_CHANGE.  
  
## Hinweise  
 Close\(\) ist eine Standardimplementierung von IAsyncInfo::Close und beinhaltet keine eigentliche Arbeit.  Um einen asynchronen Operation tatsächlich zu schließen, überschreiben Sie die reine virtuelle Methode OnClose\(\).  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)