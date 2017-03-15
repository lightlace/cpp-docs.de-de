---
title: "AsyncBase::FireCompletion-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::FireCompletion"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FireCompletion-Methode"
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::FireCompletion-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den Abschlussereignishandler auf oder legt den internen Statusdelegaten zurück.  
  
## Syntax  
  
```  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## Hinweise  
 Die erste Version von FireCompletion\(\) wird die interne Statusdelegatvariable zurück.  Die zweite Version ruft den Abschlussereignishandler auf, wenn der asynchrone Vorgang abgeschlossen ist.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)