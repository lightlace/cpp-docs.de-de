---
title: Microsoft::wrl::Wrappers::HandleTraits Namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs:
- C++
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aec9ff1b4294257f692d76a96960820379116b0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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