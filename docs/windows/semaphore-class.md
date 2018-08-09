---
title: Semaphore-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Semaphore class
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5101aba24cd8a0ed4f44587ffc4ad9e973099b8a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652635"
---
# <a name="semaphore-class"></a>Semaphore-Klasse
Stellt ein Synchronisierungsobjekt, das eine freigegebene Ressource steuert, die eine begrenzte Anzahl von Benutzern unterstützen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`SyncLock`|Ein Synonym für eine Klasse, die synchrone Sperren unterstützt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Semaphore::Semaphore-Konstruktor](../windows/semaphore-semaphore-constructor.md)|Initialisiert eine neue Instanz der dem **Semaphor** Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[InvokeHelper::Invoke-Methode](../windows/invokehelper-invoke-method.md)|Ruft den Ereignishandler, dessen Signatur mit die angegebene Anzahl von Argumenten enthält.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Semaphore::Lock-Methode](../windows/semaphore-lock-method.md)|Wartet, bis das aktuelle Objekt, oder das Objekt, das das angegebene Handle zugeordnet ist, in den signalisierten Zustand oder das angegebene Timeoutintervall verstrichen ist.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Semaphore::operator=-Operator](../windows/semaphore-operator-assign-operator.md)|Verschiebt das angegebene Handle von einem **Semaphor** -Objekt mit dem aktuellen **Semaphor** Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Semaphore`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)