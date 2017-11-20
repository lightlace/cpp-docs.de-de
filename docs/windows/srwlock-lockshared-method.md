---
title: "SRWLock::LockShared-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LockShared-Methode"
ms.assetid: 9d826a5c-b6a2-4430-ac85-d5753cbca889
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SRWLock::LockShared-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft ein SRWLock\-Objekt im gemeinsamen Modus ab.  
  
## Syntax  
  
```  
SyncLockShared LockShared();  
  
static SyncLockShared LockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### Parameter  
 `lock`  
 Zeiger zu einem SRWLock\-Objekt.  
  
## Rückgabewert  
 Ein SRWLock\-Objekt im gemeinsamen Modus.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [SRWLock\-Klasse](../windows/srwlock-class.md)