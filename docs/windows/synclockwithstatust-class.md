---
title: "SyncLockWithStatusT-Klasse"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockWithStatusT-Klasse"
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockWithStatusT-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL-Infrastruktur und ist nicht direkt aus dem Code verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `SyncTraits`  
 Ein Typ, der exklusiv ausführen kann oder den Besitz einer Ressource freigegeben.  
  
## <a name="remarks"></a>Hinweise  
 Stellt einen Typ, die exklusive durchführen können oder den Besitz einer Ressource freigegeben.  
  
 SyncLockWithStatusT-Klasse dient zum Implementieren der [Mutex](../windows/mutex-class1.md) und [Semaphore](../windows/semaphore-class.md) Klassen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Synclockwithstatust:: Synclockwithstatust-Konstruktor](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Initialisiert eine neue Instanz der SyncLockWithStatusT-Klasse.|  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Synclockwithstatust:: Synclockwithstatust-Konstruktor](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Initialisiert eine neue Instanz der SyncLockWithStatusT-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Synclockwithstatust:: GetStatus-Methode](../windows/synclockwithstatust-getstatus-method.md)|Ruft den Wait-Status des aktuellen SyncLockWithStatusT-Objekts ab.|  
|[Synclockwithstatust:: IsLocked-Methode](../windows/synclockwithstatust-islocked-method.md)|Gibt an, ob das aktuelle SyncLockWithStatusT-Objekt eine Ressource besitzt. Das SyncLockWithStatusT-Objekt ist *gesperrt*.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Synclockwithstatust:: Status_-Datenmember](../windows/synclockwithstatust-status-data-member.md)|Enthält das Ergebnis der zugrunde liegenden Wartevorgang nach einer Sperre auf ein Objekt anhand des aktuellen SyncLockWithStatusT-Objekts an.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Wrappers::Details-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)