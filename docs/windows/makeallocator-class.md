---
title: MakeAllocator-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- MakeAllocator class
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 38724e6371f5c0ae508fc18e4bc75dc2287dbe19
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="makeallocator-class"></a>MakeAllocator-Klasse
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
template<  
   typename T,  
   bool hasWeakReferenceSupport =   
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>, T)>
 class MakeAllocator;  
  
template<typename T>  
class MakeAllocator<T, false>;  
  
template<typename T>  
class MakeAllocator<T, true>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Ein Typname.  
  
 `hasWeakReferenceSupport`  
 `true` Zuweisen von Arbeitsspeicher für ein Objekt, das schwache Verweise unterstützt; `false` belegen von Speicher für ein Objekt, das schwache Verweise nicht unterstützt.  
  
## <a name="remarks"></a>Hinweise  
 Belegt Speicher für eine aktivierbare Klasse, mit oder ohne Unterstützung der schwache Verweis.  
  
 Überschreiben Sie die MakeAllocator-Klasse, um eine benutzerdefinierte Zuordnung Speichermodell implementieren.  
  
 MakeAllocator wird normalerweise verwendet, um Speicherverluste zu verhindern, wenn während der Erstellung ein Objekts auslöst.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[MakeAllocator::MakeAllocator-Konstruktor](../windows/makeallocator-makeallocator-constructor.md)|Initialisiert eine neue Instanz der MakeAllocator-Klasse.|  
|[MakeAllocator::~MakeAllocator-Destruktor](../windows/makeallocator-tilde-makeallocator-destructor.md)|Hebt die Initialisierung der aktuellen Instanz der MakeAllocator-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[MakeAllocator::Allocate-Methode](../windows/makeallocator-allocate-method.md)|Belegt Speicher aus, und ordnet dieses dem aktuellen MakeAllocator-Objekt.|  
|[MakeAllocator::Detach-Methode](../windows/makeallocator-detach-method.md)|Hebt die Zuordnung von belegten Arbeitsspeicher die [Allocate](../windows/makeallocator-allocate-method.md) Methode aus dem aktuellen MakeAllocator-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `MakeAllocator`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)