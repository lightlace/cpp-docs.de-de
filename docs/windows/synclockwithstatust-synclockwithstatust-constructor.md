---
title: "SyncLockWithStatusT::SyncLockWithStatusT-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockWithStatusT, Konstruktor"
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SyncLockWithStatusT::SyncLockWithStatusT-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
SyncLockWithStatusT(  
   _Inout_ SyncLockWithStatusT&& other  
);  
  
explicit SyncLockWithStatusT(  
   typename SyncTraits::Type sync,  
   DWORD status  
);  
```  
  
#### Parameter  
 `other`  
 Ein rvalu\-Verweis zu einem anderen SyncLockWithStatusT\-Objekt.  
  
 `sync`  
 Ein Verweis auf ein anderes SyncLockWithStatusT\-Objekt.  
  
 `status`  
 Der Wert des [status\_](../windows/synclockwithstatust-status-data-member.md) Datenmembers des `other`\-Parameters oder des `sync`\-Parameters.  
  
## Hinweise  
 Initialisiert eine neue Instanz der SyncLockWithStatusT\-Klasse.  
  
 Der erste Konstruktor initialisiert das aktuelle SyncLockWithStatusT\-Objekt von einem anderen SyncLockWithStatusT, der durch Parameter `other` angegeben wird und legt dann das andere SyncLockWithStatusT\-Objekt ungültig.  Der zweite Konstruktor ist `protected` und initialisiert das aktuelle SyncLockWithStatusT\-Objekt zu einem ungültigen Zustand.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::Details  
  
## Siehe auch  
 [SyncLockWithStatusT\-Klasse](../windows/synclockwithstatust-class.md)   
 [SyncLockWithStatusT::GetStatus\-Methode](../windows/synclockwithstatust-getstatus-method.md)