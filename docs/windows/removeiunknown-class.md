---
title: RemoveIUnknown-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
dev_langs:
- C++
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb005bc3cbf411a7d5b5ddbfa44cd6aecf802105
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="removeiunknown-class"></a>RemoveIUnknown-Klasse
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine Klasse.  
  
## <a name="remarks"></a>Hinweise  
 Stellt einen Typ, der entspricht einer `IUnknown`-Basis Typ ist jedoch nicht virtuelle `QueryInterface`, `AddRef`, und `Release` Memberfunktionen.  
  
 Standardmäßig bieten COM-Methoden virtuellen `QueryInterface`, `AddRef`, und lassen Sie die Methoden. Allerdings `ComPtr` nicht den Mehraufwand für virtuelle Methoden erfordern. `RemoveIUnknown` Dieser Aufwand durch die Bereitstellung von privaten, nicht virtuelle eliminiert `QueryInterface`, `AddRef`, und `Release` Methoden.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`ReturnType`|Ein Synonym für einen Typ, der Vorlagenparameter entspricht `T` , hat jedoch nicht virtuelle IUnknown-Member.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `T`  
  
 `RemoveIUnknown`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)