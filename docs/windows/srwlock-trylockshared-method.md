---
title: "SRWLock::TryLockShared-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLockShared-Methode"
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SRWLock::TryLockShared-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Versuche, ein SRWLock\-Objekt im gemeinsamen Modus für den aktuellen oder das angegebene SRWLock\-Objekt abzurufen.  
  
## Syntax  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### Parameter  
 `lock`  
 Zeiger zu einem SRWLock\-Objekt.  
  
## Rückgabewert  
 Wenn erfolgreich, wird ein SRWLock\-Objekt im gemeinsamen Modus und der aufrufende Thread Besitz der Sperre.  Andernfalls SRWLock\-Objekt ein, dessen Zustand NULL ist.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [SRWLock\-Klasse](../windows/srwlock-class.md)