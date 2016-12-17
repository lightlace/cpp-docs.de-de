---
title: "AsyncBase::TryTransitionToError-Methode"
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
  - "async/Microsoft::WRL::AsyncBase::TryTransitionToError"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryTransitionToError-Methode"
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
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