---
title: HandleT-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT class
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99a596bf1e086ac7b1a1a72c3504ce4f41844ba4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="handlet-class"></a>HandleT-Klasse
Stellt ein Handle für ein Objekt dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename HandleTraits  
>  
class HandleT;  
```  
  
#### <a name="parameters"></a>Parameter  
 `HandleTraits`  
 Eine Instanz von der [HandleTraits](../windows/handletraits-structure.md) Struktur, die allgemeinen Eigenschaften eines Handles definiert.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`Traits`|Ein Synonym für `HandleTraits`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HandleT::HandleT-Konstruktor](../windows/handlet-handlet-constructor.md)|Initialisiert eine neue Instanz der HandleT-Klasse.|  
|[HandleT::~HandleT-Destruktor](../windows/handlet-tilde-handlet-destructor.md)|Hebt die Initialisierung einer Instanz der HandleT-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HandleT::Attach-Methode](../windows/handlet-attach-method.md)|Ordnet das angegebene Handle mit dem aktuellen HandleT-Objekt.|  
|[HandleT::Close-Methode](../windows/handlet-close-method.md)|Schließt das aktuelle HandleT-Objekt.|  
|[HandleT::Detach-Methode](../windows/handlet-detach-method.md)|Hebt die Zuordnung der aktuellen HandleT-Objekts aus der zugrunde liegende Handle.|  
|[HandleT::Get-Methode](../windows/handlet-get-method.md)|Ruft den Wert des zugrunde liegenden Handles ab.|  
|[HandleT::IsValid-Methode](../windows/handlet-isvalid-method.md)|Gibt an, ob das aktuelle HandleT-Objekt ein Handle darstellt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HandleT::InternalClose-Methode](../windows/handlet-internalclose-method.md)|Schließt das aktuelle HandleT-Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HandleT::operator=-Operator](../windows/handlet-operator-assign-operator.md)|Verschiebt den Wert des angegebenen HandleT-Objekts mit dem aktuellen HandleT-Objekt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[HandleT::handle_ Data-Member](../windows/handlet-handle-data-member.md)|Enthält das Handle, das vom HandleT-Objekt dargestellt wird.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `HandleT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)