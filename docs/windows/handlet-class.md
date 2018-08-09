---
title: HandleT-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: a34b66a6e2c901ddbfb3005a0bdb8fd686317af0
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641504"
---
# <a name="handlet-class"></a>HandleT-Klasse
Stellt ein Handle für ein Objekt dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <  
   typename HandleTraits  
>  
class HandleT;  
```  
  
### <a name="parameters"></a>Parameter  
 *HandleTraits*  
 Eine Instanz von der [HandleTraits](../windows/handletraits-structure.md) abgeschrägten Designs, die allgemeinen Eigenschaften eines Handles definiert.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`Traits`|Ein Synonym für `HandleTraits`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HandleT::HandleT-Konstruktor](../windows/handlet-handlet-constructor.md)|Initialisiert eine neue Instanz der dem **HandleT** Klasse.|  
|[HandleT::~HandleT-Destruktor](../windows/handlet-tilde-handlet-destructor.md)|Hebt die Initialisierung einer Instanz von der **HandleT** Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HandleT::Attach-Methode](../windows/handlet-attach-method.md)|Ordnet das angegebene Handle der aktuellen **HandleT** Objekt.|  
|[HandleT::Close-Methode](../windows/handlet-close-method.md)|Schließt das aktuelle **HandleT** Objekt.|  
|[HandleT::Detach-Methode](../windows/handlet-detach-method.md)|Hebt die Zuordnung der aktuellen **HandleT** Objekt aus der zugrunde liegende Handle.|  
|[HandleT::Get-Methode](../windows/handlet-get-method.md)|Ruft den Wert, der das zugrunde liegende Handle.|  
|[HandleT::IsValid-Methode](../windows/handlet-isvalid-method.md)|Gibt an, ob die aktuelle **HandleT** Objekt stellt ein Handle.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HandleT::InternalClose-Methode](../windows/handlet-internalclose-method.md)|Schließt das aktuelle **HandleT** Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HandleT::operator=-Operator](../windows/handlet-operator-assign-operator.md)|Verschiebt den Wert des angegebenen **HandleT** -Objekt mit dem aktuellen **HandleT** Objekt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[HandleT::handle_ Data-Member](../windows/handlet-handle-data-member.md)|Enthält das Handle, das entspricht dem **HandleT** Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `HandleT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)