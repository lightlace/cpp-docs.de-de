---
title: SRWLock-Klasse | Microsoft Docs
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
ms.openlocfilehash: ec31b1469f437ff2776ed9da52fbcd7557fca8e2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891752"
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