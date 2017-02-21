---
title: "AsyncBase::TryTransitionToError-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::TryTransitionToError"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryTransitionToError-Methode"
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::TryTransitionToError-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob der angegebene Fehlercode den Zustand des internen Fehlers ändern kann.  
  
## Syntax  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### Parameter  
 `error`  
 Ein Fehler HRESULT.  
  
## Rückgabewert  
 `true`, wenn der interne Zustand des Fehlers geändert wurde; andernfalls `false`.  
  
## Hinweise  
 Dieser Vorgang ändert den Fehlerzustand nur, wenn der Fehlerzustand bereits auf S\_OK festgelegt wird.  Dieser Vorgang wirkt, wenn der Fehlerzustand bereits Fehler ist, abgebrochen, abgeschlossen, oder geschlossen.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)