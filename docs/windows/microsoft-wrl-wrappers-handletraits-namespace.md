---
title: Microsoft::wrl::Wrappers::HandleTraits Namespace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs:
- C++
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b114d067249e78d7fb935e473cc3cc952c76fe02
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878033"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits-Namespace
Beschreibt die Merkmale von allgemeinen Handle basierende Ressourcentypen zur Verfügung.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>Member  
  
### <a name="structures"></a>Strukturen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CriticalSectionTraits-Struktur](../windows/criticalsectiontraits-structure.md)|Spezialisiert eine `CriticalSection` Objekts zur Unterstützung einer ungültigen kritischen Abschnitt oder eine Funktion zum Freigeben eines kritischen Abschnitts.|  
|[EventTraits-Struktur](../windows/eventtraits-structure.md)|Definiert die Eigenschaften einer `Event` Klassenhandle.|  
|[FileHandleTraits-Struktur](../windows/filehandletraits-structure.md)|Definiert die Eigenschaften des ein Dateihandle.|  
|[HANDLENullTraits-Struktur](../windows/handlenulltraits-structure.md)|Definiert die gemeinsame Merkmale eines Handles nicht initialisiert.|  
|[HANDLETraits-Struktur](../windows/handletraits-structure.md)|Definiert die gemeinsame Merkmale eines Handles.|  
|[MutexTraits-Struktur](../windows/mutextraits-structure.md)|Definiert die gemeinsame Merkmale der [Mutex](../windows/mutex-class1.md) Klasse.|  
|[SemaphoreTraits-Struktur](../windows/semaphoretraits-structure.md)|Definiert die gemeinsame Merkmale eines Semaphore-Objekts.|  
|[SRWLockExclusiveTraits-Struktur](../windows/srwlockexclusivetraits-structure.md)|Beschreibt allgemeine Merkmale der `SRWLock` Klasse im Sperrmodus für exklusive.|  
|[SRWLockSharedTraits-Struktur](../windows/srwlocksharedtraits-structure.md)|Beschreibt allgemeine Merkmale der `SRWLock` Klasse im freigegebenen Modus.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)