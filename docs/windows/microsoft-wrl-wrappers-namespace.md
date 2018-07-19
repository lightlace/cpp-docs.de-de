---
title: Microsoft::wrl::Wrappers Namespace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
dev_langs:
- C++
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fa666c1a5de2962a4479b355966c1e8282f2989b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878280"
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers-Namespace
Definiert die Wrappertypen von Resource Acquisition ist Initialisierung (RAII)-, die die Verwaltung der Lebensdauer von Objekten, Zeichenfolgen und Handles zu vereinfachen.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace Microsoft::WRL::Wrappers;  
```  
  
## <a name="members"></a>Member  
  
### <a name="typedefs"></a>Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|  
  
### <a name="classes"></a>Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CriticalSection-Klasse](../windows/criticalsection-class.md)|Stellt ein kritisches Abschnittsobjekt dar.|  
|[Ereignisklasse (C++-Vorlagenbibliothek der Windows-Runtime)](../windows/event-class-windows-runtime-cpp-template-library.md)|Stellt ein Ereignis dar.|  
|[HandleT-Klasse](../windows/handlet-class.md)|Stellt ein Handle für ein Objekt dar.|  
|[HString-Klasse](../windows/hstring-class.md)|Bietet Unterstützung für die Bearbeitung von HSTRING-Handles.|  
|[HStringReference-Klasse](../windows/hstringreference-class.md)|Stellt ein HSTRING dar, das aus einer vorhandenen Zeichenfolge erstellt wird.|  
|[Mutex-Klasse](../windows/mutex-class1.md)|Stellt ein Synchronisierungsobjekt, das ausschließlich auf eine freigegebene Ressource steuert.|  
|[RoInitializeWrapper-Klasse](../windows/roinitializewrapper-class.md)|Initialisiert die Windows-Runtime.|  
|[Semaphore-Klasse](../windows/semaphore-class.md)|Stellt ein Synchronisierungsobjekt, das eine freigegebene Ressource steuert, die eine begrenzte Anzahl von Benutzern unterstützen können.|  
|[SRWLock-Klasse](../windows/srwlock-class.md)|Stellt eine slim Reader/Writer-Sperre.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)