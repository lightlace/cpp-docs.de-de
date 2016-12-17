---
title: "Mutex-Klasse"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Mutex-Klasse"
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# Mutex-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Synchronisierungsobjekt dar, das ausschließlich eine freigegebene Ressource gesteuert wird.  
  
## Syntax  
  
```  
class Mutex : public HandleT<HandleTraits::MutexTraits>  
  
```  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|**SyncLock**|Ein Synonym für eine Klasse, die synchrone Sperren unterstützt.|  
  
### Öffentlicher Konstruktor  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Mutex::Mutex\-Konstruktor](../windows/mutex-mutex-constructor.md)|Initialisiert eine neue Instanz der Mutexklasse.|  
  
### Öffentliche Member  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Mutex::Lock\-Methode](../windows/mutex-lock-method.md)|wartet, bis das aktuelle Objekt oder das Mutex\-Objekt, das mit dem gegebenen Handle, den Versionen der Mutex oder dem angegebenen Timeoutintervall zugeordnet wird, verstrichen ist.|  
  
### Öffentlicher Operator  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Mutex::operator\=\-Operator](../windows/mutex-operator-assign-operator.md)|Weist \(Wechselt\) das angegebene Mutex\-Objekt zum aktuellen Mutex\-Objekt zu.|  
  
## Vererbungshierarchie  
 `Mutex`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers\-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)