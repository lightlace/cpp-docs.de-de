---
title: "SyncLockT::IsLocked-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsLocked-Methode"
ms.assetid: a81fea43-f99a-4708-812a-7fd6af500d3d
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SyncLockT::IsLocked-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
bool IsLocked() const;  
```  
  
## Rückgabewert  
 **true**, wenn das SyncLockT\-Objekt gesperrt wird; andernfalls **false**.  
  
## Hinweise  
 Gibt an, ob das aktuelle SyncLockT\-Objekt eine Ressource besitzt; das bedeutet, dass das SyncLockT\-Objekt *gesperrt*.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::Details  
  
## Siehe auch  
 [SyncLockT\-Klasse](../windows/synclockt-class.md)