---
title: SRWLock-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
dev_langs:
- C++
helpviewer_keywords:
- SRWLock class
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58b537a29a042f2227f3c2c121a320532d52877c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016365"
---
# <a name="srwlock-class"></a>SRWLock-Klasse
Stellt eine slim Reader-/Writer-Sperre.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
class SRWLock;  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine slim Reader-/Writer-Sperre wird zum Synchronisieren des Zugriffs über Threads auf ein Objekt oder eine Ressource verwendet. Weitere Informationen finden Sie unter [Synchronisierungsfunktionen](http://msdn.microsoft.com/9b6359c2-0113-49b6-83d0-316ad95aba1b).  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|||  
|-|-|  
|`SyncLockExclusive`|Synonym für einen **SRWLock** -Objekt, das im exklusiven Modus abgerufen wird.|  
|`SyncLockShared`|Synonym für einen **SRWLock** -Objekt, das im freigegebenen Modus abgerufen wird.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SRWLock::SRWLock-Konstruktor](../windows/srwlock-srwlock-constructor.md)|Initialisiert eine neue Instanz der dem **SRWLock** Klasse.|  
|[SRWLock::~SRWLock-Destruktor](../windows/srwlock-tilde-srwlock-destructor.md)|Hebt die Initialisierung einer Instanz von der **SRWLock** Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SRWLock::LockExclusive-Methode](../windows/srwlock-lockexclusive-method.md)|Ruft eine **SRWLock** Objekt im exklusiven Modus.|  
|[SRWLock::LockShared-Methode](../windows/srwlock-lockshared-method.md)|Ruft eine **SRWLock** Objekt im freigegebenen Modus.|  
|[SRWLock::TryLockExclusive-Methode](../windows/srwlock-trylockexclusive-method.md)|Versucht, für eine **SRWLock** Objekt im exklusiven Modus für den aktuellen oder angegebenen **SRWLock** Objekt.|  
|[SRWLock::TryLockShared-Methode](../windows/srwlock-trylockshared-method.md)|Versucht, für eine **SRWLock** Objekt im freigegebenen Modus für den aktuellen oder angegebenen **SRWLock** Objekt.|  
  
### <a name="protected-data-member"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[SRWLock::SRWLock_ Data-Member](../windows/srwlock-srwlock-data-member.md)|Enthält die zugrunde liegende Sperre-Variable für den aktuellen **SRWLock** Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `SRWLock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)