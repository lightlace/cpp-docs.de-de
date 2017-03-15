---
title: "SRWLock::TryLockExclusive-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLockExclusive-Methode"
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SRWLock::TryLockExclusive-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Versuche, ein SRWLock\-Objekt im exklusiven Modus für den aktuellen oder das angegebene SRWLock\-Objekt abzurufen.  Wenn der Aufruf erfolgreich ist, wird der aufrufende Thread Besitz der Sperre.  
  
## Syntax  
  
```  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### Parameter  
 `lock`  
 Zeiger zu einem SRWLock\-Objekt.  
  
## Rückgabewert  
 Wenn erfolgreich, wird ein SRWLock\-Objekt im exklusiven Modus und der aufrufende Thread Besitz der Sperre.  Andernfalls SRWLock\-Objekt ein, dessen Zustand NULL ist.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [SRWLock\-Klasse](../windows/srwlock-class.md)