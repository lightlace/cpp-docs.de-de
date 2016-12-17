---
title: "SyncLockT::SyncLockT-Konstruktor"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockT, Konstruktor"
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockT::SyncLockT-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
SyncLockT(  
   _Inout_ SyncLockT&& other  
);  
  
explicit SyncLockT(  
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);  
```  
  
#### Parameter  
 `other`  
 Ein rvalu\-Verweis zu einem anderen SyncLockT\-Objekt.  
  
 `sync`  
 Ein Verweis auf ein anderes SyncLockWithStatusT\-Objekt.  
  
## Hinweise  
 Initialisiert eine neue Instanz der SyncLockT\-Klasse.  
  
 Der erste Konstruktor initialisiert das aktuelle SyncLockT\-Objekt von einem anderen SyncLockT\-Objekt, das durch Parameter `other` angegeben wird und legt dann das andere SyncLockT\-Objekt ungültig.  Der zweite Konstruktor ist `protected` und initialisiert das aktuelle SyncLockT\-Objekt zu einem ungültigen Zustand.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::Details  
  
## Siehe auch  
 [SyncLockT\-Klasse](../windows/synclockt-class.md)