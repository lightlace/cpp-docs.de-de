---
title: SRWLock-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
dev_langs:
- C++
helpviewer_keywords:
- SRWLock class
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1325a089739b3820009aa239f56805264dbb6b83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="srwlock-class"></a>SRWLock-Klasse
Stellt eine slim Reader/Writer-Sperre.  
  
## <a name="syntax"></a>Syntax  
  
```  
class SRWLock;  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine slim Reader/Writer-Sperre wird zum Synchronisieren des Zugriffs auf ein Objekt oder eine Ressource threadübergreifend verwendet. Weitere Informationen finden Sie unter [Synchronisierungsfunktionen](http://msdn.microsoft.com/en-us/9b6359c2-0113-49b6-83d0-316ad95aba1b).  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|||  
|-|-|  
|**SyncLockExclusive**|Synonym für ein SRWLock-Objekt, das im exklusiven Modus abgerufen wird.|  
|**SyncLockShared**|Synonym für ein SRWLock-Objekt, das im freigegebenen Modus abgerufen wird.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SRWLock::SRWLock-Konstruktor](../windows/srwlock-srwlock-constructor.md)|Initialisiert eine neue Instanz der SRWLock-Klasse.|  
|[SRWLock::~SRWLock-Destruktor](../windows/srwlock-tilde-srwlock-destructor.md)|Hebt die Initialisierung einer Instanz der SRWLock-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SRWLock::LockExclusive-Methode](../windows/srwlock-lockexclusive-method.md)|Ruft ein Objekt SRWLock, im exklusiven Modus ab.|  
|[SRWLock::LockShared-Methode](../windows/srwlock-lockshared-method.md)|Ruft ein Objekt SRWLock im freigegebenen Modus ab.|  
|[SRWLock::TryLockExclusive-Methode](../windows/srwlock-trylockexclusive-method.md)|Versucht, ein SRWLock-Objekt im exklusiven Modus für das aktuelle oder angegebene SRWLock-Objekt zu erhalten.|  
|[SRWLock::TryLockShared-Methode](../windows/srwlock-trylockshared-method.md)|Versucht, ein SRWLock-Objekt im freigegebenen Modus für das aktuelle oder angegebene SRWLock-Objekt zu erhalten.|  
  
### <a name="protected-data-member"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[SRWLock::SRWLock_ Data-Member](../windows/srwlock-srwlock-data-member.md)|Enthält die zugrunde liegenden Sperren der Variable für das aktuelle SRWLock-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `SRWLock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)