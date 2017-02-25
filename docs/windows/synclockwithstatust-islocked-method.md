---
title: "SyncLockWithStatusT::IsLocked-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsLocked-Methode"
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SyncLockWithStatusT::IsLocked-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
bool IsLocked() const;  
```  
  
## Hinweise  
 Gibt an, ob das aktuelle SyncLockWithStatusT\-Objekt eine Ressource besitzt; das bedeutet, dass das SyncLockWithStatusT\-Objekt *gesperrt*.  
  
## Rückgabewert  
 **true**, wenn das SyncLockWithStatusT\-Objekt gesperrt wird; andernfalls **false**.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::Details  
  
## Siehe auch  
 [SyncLockWithStatusT\-Klasse](../windows/synclockwithstatust-class.md)