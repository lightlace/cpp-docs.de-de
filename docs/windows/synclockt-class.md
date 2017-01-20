---
title: "SyncLockT-Klasse"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockT-Klasse"
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockT-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
#### Parameter  
 `SyncTraits`  
 Der Typ, der den Besitz einer Ressource verwenden kann.  
  
## Hinweise  
 Stellt einen Typ dar, der den Status Exclusive oder gemeinschaftliches Eigentum eine Ressource verwenden kann.  
  
 Die SyncLockT\-Klasse wird beispielsweise verwendet, ob die [SRWLock](../windows/srwlock-class.md)\-Klasse implementieren.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SyncLockT::SyncLockT\-Konstruktor](../windows/synclockt-synclockt-constructor.md)|Initialisiert eine neue Instanz der SyncLockT\-Klasse.|  
|[SyncLockT::~SyncLockT\-Destruktor](../windows/synclockt-tilde-synclockt-destructor.md)|Deinitialisiert eine Instanz der SyncLockT\-Klasse.|  
  
### Geschützte Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SyncLockT::SyncLockT\-Konstruktor](../windows/synclockt-synclockt-constructor.md)|Initialisiert eine neue Instanz der SyncLockT\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SyncLockT::IsLocked\-Methode](../windows/synclockt-islocked-method.md)|Gibt an, ob das aktuelle SyncLockT\-Objekt eine Ressource besitzt; das bedeutet, dass das SyncLockT\-Objekt *gesperrt*.|  
|[SyncLockT::Unlock\-Method](../windows/synclockt-unlock-method.md)|Versionssteuerelement der Ressource unterbrochen durch das aktuelle SyncLockT\-Objekt, sofern vorhanden.|  
  
### Geschützte Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SyncLockT::sync\_\-Datenmember](../windows/synclockt-sync-data-member.md)|Hält die zugrunde liegende Ressource dargestellt durch die SyncLockT\-Klasse an.|  
  
## Vererbungshierarchie  
 `SyncLockT`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::Details  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers::Details\-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock\-Klasse](../windows/srwlock-class.md)