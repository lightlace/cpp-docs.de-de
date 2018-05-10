---
title: SyncLockT-Klasse | Microsoft Docs
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
ms.openlocfilehash: e05a1be5d84db52573d3c3235936ecf82dde5894
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="synclockt-class"></a>SyncLockT-Klasse
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
#### <a name="parameters"></a>Parameter  
 `SyncTraits`  
 Der Typ, der Besitzer einer Ressource werden kann.  
  
## <a name="remarks"></a>Hinweise  
 Einen Typ, der exklusiven werfen darstellt oder den gemeinsamen Besitz einer Ressource.  
  
 SyncLockT-Klasse wird verwendet, z. B. zum Implementieren der [SRWLock](../windows/srwlock-class.md) Klasse.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SyncLockT::SyncLockT-Konstruktor](../windows/synclockt-synclockt-constructor.md)|Initialisiert eine neue Instanz der SyncLockT-Klasse.|  
|[SyncLockT::~SyncLockT-Destruktor](../windows/synclockt-tilde-synclockt-destructor.md)|Hebt die Initialisierung einer Instanz der SyncLockT-Klasse.|  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SyncLockT::SyncLockT-Konstruktor](../windows/synclockt-synclockt-constructor.md)|Initialisiert eine neue Instanz der SyncLockT-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SyncLockT::IsLocked-Methode](../windows/synclockt-islocked-method.md)|Gibt an, ob das aktuelle SyncLockT-Objekt eine Ressource besitzt. SyncLockT-Objekt ist *gesperrt*.|  
|[SyncLockT::Unlock-Method](../windows/synclockt-unlock-method.md)|Kontrolle über die Ressource frei, die für das aktuelle SyncLockT-Objekt frei, sofern vorhanden.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[SyncLockT::sync_-Datenmember](../windows/synclockt-sync-data-member.md)|Enthält die zugrunde liegende Ressource, die durch die SyncLockT-Klasse dargestellt wird.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `SyncLockT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Wrappers::Details-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock-Klasse](../windows/srwlock-class.md)