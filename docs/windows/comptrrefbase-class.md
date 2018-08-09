---
title: ComPtrRefBase-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRefBase class
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18f7f08362c14ab0d09019a5b9348750c96ddbd7
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643409"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase-Klasse
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Ein [ComPtr\<T >](../windows/comptr-class.md) Typ oder einem Typ abgeleitet ist, nicht nur die Schnittstelle der **ComPtr**.  
  
## <a name="remarks"></a>Hinweise  
 Stellt die Basisklasse für die [ComPtrRef](../windows/comptrref-class.md) Klasse.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`InterfaceType`|Ein Synonym für den Typ des Vorlagenparameters *T*.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ComPtrRefBase::operator IInspectable**-Operator](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|Wandelt das aktuelle [Ptr_](../windows/comptrrefbase-ptr-data-member.md) Datenmembers, der einen Zeiger an eine-Zeiger-an die `IInspectable` Schnittstelle.|  
|[ComPtrRefBase::operator IUnknown**-Operator](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|Wandelt das aktuelle [Ptr_](../windows/comptrrefbase-ptr-data-member.md) Datenmembers, der einen Zeiger an eine-Zeiger-an die `IUnknown` Schnittstelle.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[ComPtrRefBase::ptr_-Datenmember](../windows/comptrrefbase-ptr-data-member.md)|Zeiger auf den Typ, durch den aktuellen Vorlagenparameter angegeben.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ComPtrRefBase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)