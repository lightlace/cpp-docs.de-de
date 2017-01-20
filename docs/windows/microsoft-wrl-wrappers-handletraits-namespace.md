---
title: "Microsoft::WRL::Wrappers::HandleTraits-Namespace"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HandleTraits-Namespace"
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Microsoft::WRL::Wrappers::HandleTraits-Namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt die Eigenschaften von allgemeinen Handle basierender Ressourcentypen.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="structures"></a>Strukturen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CriticalSectionTraits-Struktur](../windows/criticalsectiontraits-structure.md)|Spezialisiert ist ein `CriticalSection` -Objekt einen ungültigen kritischen Bereich oder eine Funktion zum Freigeben eines kritischen Abschnitts zu unterstützen.|  
|[EventTraits-Struktur](../windows/eventtraits-structure.md)|Definiert Eigenschaften einer `Event` Klassenhandle.|  
|[FileHandleTraits-Struktur](../windows/filehandletraits-structure.md)|Definiert die Eigenschaften eines Dateihandles.|  
|[HANDLENullTraits-Struktur](../windows/handlenulltraits-structure.md)|Definiert die gemeinsamen Merkmale eines nicht initialisierten Handles.|  
|[HANDLETraits-Struktur](../windows/handletraits-structure.md)|Definiert die gemeinsamen Merkmale eines Handles.|  
|[MutexTraits-Struktur](../windows/mutextraits-structure.md)|Definiert die gemeinsamen Merkmale der [Mutex](../windows/mutex-class1.md) Klasse.|  
|[SemaphoreTraits-Struktur](../windows/semaphoretraits-structure.md)|Definiert die gemeinsame Merkmale eines Semaphore-Objekts.|  
|[SRWLockExclusiveTraits-Struktur](../windows/srwlockexclusivetraits-structure.md)|Beschreibt allgemeine Merkmale der `SRWLock` Klasse im exklusiven Modus.|  
|[SRWLockSharedTraits-Struktur](../windows/srwlocksharedtraits-structure.md)|Beschreibt allgemeine Merkmale der `SRWLock` Klasse im freigegebenen Modus.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)