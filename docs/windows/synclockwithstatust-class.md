---
title: SyncLockWithStatusT-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT class
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 51e5a66358890fc20731fb5cb657616484e19db4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890979"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT-Klasse
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `SyncTraits`  
 Ein Typ, der exklusiven werfen oder den gemeinsamen Besitz einer Ressource.  
  
## <a name="remarks"></a>Hinweise  
 Einen Typ, der exklusiven werfen darstellt oder den gemeinsamen Besitz einer Ressource.  
  
 SyncLockWithStatusT-Klasse wird zum Implementieren der [Mutex](../windows/mutex-class1.md) und [Semaphore](../windows/semaphore-class.md) Klassen.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT-Konstruktor](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Initialisiert eine neue Instanz der SyncLockWithStatusT-Klasse.|  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT-Konstruktor](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Initialisiert eine neue Instanz der SyncLockWithStatusT-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SyncLockWithStatusT::GetStatus-Methode](../windows/synclockwithstatust-getstatus-method.md)|Ruft den Wait-Status des aktuellen SyncLockWithStatusT-Objekts ab.|  
|[SyncLockWithStatusT::IsLocked-Methode](../windows/synclockwithstatust-islocked-method.md)|Gibt an, ob das aktuelle SyncLockWithStatusT-Objekt eine Ressource besitzt. SyncLockWithStatusT-Objekt ist *gesperrt*.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[SyncLockWithStatusT::status_-Datenmember](../windows/synclockwithstatust-status-data-member.md)|Enthält das Ergebnis der zugrunde liegenden Wartevorgang nach einer Sperre auf Grundlage des aktuellen SyncLockWithStatusT-Objekts ein Objekt zu.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers::Details-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)