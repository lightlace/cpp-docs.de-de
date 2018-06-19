---
title: ComPtrRefBase-Klasse | Microsoft Docs
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
ms.openlocfilehash: 13744a1629ede5575dc992ea15b90e22961a8570
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883579"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase-Klasse
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Ein [ComPtr\<T >](../windows/comptr-class.md) Typ "oder" daraus abgeleitete, nicht nur die Schnittstelle, die durch das comptr-Objekt dargestellt wird.  
  
## <a name="remarks"></a>Hinweise  
 Stellt die Basisklasse für die [ComPtrRef](../windows/comptrref-class.md) Klasse.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`InterfaceType`|Ein Synonym für den Typ des Vorlagenparameters `T`.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ComPtrRefBase::operator IInspectable**-Operator](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|Wandelt das aktuelle [Ptr_](../windows/comptrrefbase-ptr-data-member.md) -Datenmember auf einen Zeiger-auf-a-Zeiger-to "iinspectable"-Schnittstelle.|  
|[ComPtrRefBase::operator IUnknown**-Operator](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|Wandelt das aktuelle [Ptr_](../windows/comptrrefbase-ptr-data-member.md) -Datenmember auf einen Zeiger an eine-Zeiger-an der IUnknown-Schnittstelle.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[ComPtrRefBase::ptr_-Datenmember](../windows/comptrrefbase-ptr-data-member.md)|Zeiger auf den Typ, der durch den aktuellen Vorlagenparameter angegeben.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ComPtrRefBase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)