---
title: SyncLockT-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f6b27f45d3a9b9b308a56e1ac8f945969f8c49e2
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643425"
---
# <a name="synclockt-class"></a>SyncLockT-Klasse
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
### <a name="parameters"></a>Parameter  
 *SyncTraits*  
 Der Typ, der Besitz einer Ressource übernehmen kann.  
  
## <a name="remarks"></a>Hinweise  
 Stellt einen Typ, der exklusiven annehmen kann, oder den gemeinsamen Besitz einer Ressource.  
  
 Die **SyncLockT** Klasse wird verwendet, z. B. zum Implementieren der [SRWLock](../windows/srwlock-class.md) Klasse.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SyncLockT::SyncLockT-Konstruktor](../windows/synclockt-synclockt-constructor.md)|Initialisiert eine neue Instanz der dem **SyncLockT** Klasse.|  
|[SyncLockT::~SyncLockT-Destruktor](../windows/synclockt-tilde-synclockt-destructor.md)|Hebt die Initialisierung einer Instanz von der **SyncLockT** Klasse.|  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SyncLockT::SyncLockT-Konstruktor](../windows/synclockt-synclockt-constructor.md)|Initialisiert eine neue Instanz der dem **SyncLockT** Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SyncLockT::IsLocked-Methode](../windows/synclockt-islocked-method.md)|Gibt an, ob die aktuelle **SyncLockT** Objekt besitzt eine Ressource, d. h. die **SyncLockT** Objekt *gesperrt*.|  
|[SyncLockT::Unlock-Method](../windows/synclockt-unlock-method.md)|Gibt die Steuerung der Ressource frei, die von der aktuellen frei **SyncLockT** Objekt, sofern vorhanden.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[SyncLockT::sync_-Datenmember](../windows/synclockt-sync-data-member.md)|Enthält die zugrunde liegende Ressource dargestellt wird, durch die **SyncLockT** Klasse.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `SyncLockT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Wrappers::Details-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock-Klasse](../windows/srwlock-class.md)