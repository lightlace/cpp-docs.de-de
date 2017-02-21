---
title: "SRWLock-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLock-Klasse"
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# SRWLock-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt einen Slim Reader\/Writer\-Sperre dar.  
  
## Syntax  
  
```  
class SRWLock;  
```  
  
## Hinweise  
 Ein einfacher Reader\/Writer\-Sperre wird verwendet, um Zugriff über Threads auf ein Objekt oder Ressource zu synchronisieren.  Weitere Informationen finden Sie unter [Synchronisierungs\-Funktionen](assetId:///9b6359c2-0113-49b6-83d0-316ad95aba1b) in der MSDN Library.  
  
## Member  
  
### Öffentliche Typedefs  
  
|||  
|-|-|  
|**SyncLockExclusive**|Synonym für ein SRWLock\-Objekt, im exklusiven Modus abgerufen wird.|  
|**SyncLockShared**|Synonym für ein SRWLock\-Objekt, das im gemeinsamen Modus abgerufen wird.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SRWLock::SRWLock\-Konstruktor](../windows/srwlock-srwlock-constructor.md)|Initialisiert eine neue Instanz der SRWLock\-Klasse.|  
|[SRWLock::~SRWLock\-Destruktor](../windows/srwlock-tilde-srwlock-destructor.md)|Deinitialisiert eine Instanz der SRWLock\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SRWLock::LockExclusive\-Methode](../windows/srwlock-lockexclusive-method.md)|Ruft ein SRWLock\-Objekt im exklusiven Modus ab.|  
|[SRWLock::LockShared\-Methode](../windows/srwlock-lockshared-method.md)|Ruft ein SRWLock\-Objekt im gemeinsamen Modus ab.|  
|[SRWLock::TryLockExclusive\-Methode](../windows/srwlock-trylockexclusive-method.md)|Versuche, ein SRWLock\-Objekt im exklusiven Modus für den aktuellen oder das angegebene SRWLock\-Objekt abzurufen.|  
|[SRWLock::TryLockShared\-Methode](../windows/srwlock-trylockshared-method.md)|Versuche, ein SRWLock\-Objekt im gemeinsamen Modus für den aktuellen oder das angegebene SRWLock\-Objekt abzurufen.|  
  
### Geschützter Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SRWLock::SRWLock\_ Data\-Member](../windows/srwlock-srwlock-data-member.md)|Enthält die zugrunde liegende Sperrenvariable für das aktuelle SRWLock\-Objekt.|  
  
## Vererbungshierarchie  
 `SRWLock`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers\-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)