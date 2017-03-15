---
title: "Microsoft::WRL::Wrappers-Namespace | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Wrappers-Namespace"
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Microsoft::WRL::Wrappers-Namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert die Wrappertypen von Resource Acquisition ist Initialisierung (RAII)-, die die Verwaltung der Lebensdauer von Objekten, Zeichenfolgen und Handles zu vereinfachen.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace Microsoft::WRL::Wrappers;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="typedefs"></a>Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|  
  
### <a name="classes"></a>Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Critical_section-Klasse](../windows/criticalsection-class.md)|Stellt ein kritisches Abschnittsobjekt dar.|  
|[Event-Klasse (Windows Runtime C++-Vorlagenbibliothek)](../windows/event-class-windows-runtime-cpp-template-library.md)|Stellt ein Ereignis dar.|  
|[HandleT-Klasse](../windows/handlet-class.md)|Stellt ein Handle für ein Objekt dar.|  
|[HString-Klasse](../windows/hstring-class.md)|Bietet Unterstützung für die Bearbeitung von HSTRING-Handles.|  
|[HStringReference-Klasse](../windows/hstringreference-class.md)|Stellt ein HSTRING dar, das aus einer vorhandenen Zeichenfolge erstellt wird.|  
|[Mutex-Klasse](../windows/mutex-class1.md)|Stellt ein Synchronisierungsobjekt, das ausschließlich auf eine freigegebene Ressource steuert.|  
|[RoInitializeWrapper-Klasse](../windows/roinitializewrapper-class.md)|Initialisiert das [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
|[Semaphore-Klasse](../windows/semaphore-class.md)|Stellt ein Synchronisierungsobjekt, das eine freigegebene Ressource steuert, die eine begrenzte Anzahl von Benutzern unterstützen kann.|  
|[SRWLock-Klasse](../windows/srwlock-class.md)|Stellt eine slim Reader-/Writer-Sperre.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft:: wrl-Namespace](../windows/microsoft-wrl-namespace.md)