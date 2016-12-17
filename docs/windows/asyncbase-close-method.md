---
title: "AsyncBase::Close-Methode"
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
  - "async/Microsoft::WRL::AsyncBase::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close-Methode"
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
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