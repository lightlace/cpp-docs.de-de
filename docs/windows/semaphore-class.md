---
title: "Semaphore-Klasse"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Semaphore-Klasse"
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Semaphore-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Synchronisierungsobjekt dar, das eine freigegebene Ressource gesteuert wird, die eine beschränkte Anzahl Benutzer unterstützen kann.  
  
## Syntax  
  
```  
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>  
```  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`SyncLock`|Ein Synonym für eine Klasse, die synchrone Sperren unterstützt.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Semaphore::Semaphore\-Konstruktor](../windows/semaphore-semaphore-constructor.md)|Initialisiert eine neue Instanz der Semaphorenklasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[InvokeHelper::Invoke\-Methode](../windows/invokehelper-invoke-method.md)|Ruft den Ereignishandler auf, dessen Signatur die angegebene Anzahl von Argumenten enthält.|  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Semaphore::Lock\-Methode](../windows/semaphore-lock-method.md)|wartet, bis das aktuelle Objekt oder das Objekt, das dem angegebenen Handle zugeordnet ist, im signalisierten Zustand oder angegebenen Timeoutintervall ist, verstrichen ist.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Semaphore::operator\=\-Operator](../windows/semaphore-operator-assign-operator.md)|Verschiebt das angegebene Handle von einem Semaphorobjekt dem aktuellen Semaphorobjekt.|  
  
## Vererbungshierarchie  
 `Semaphore`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers\-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)