---
title: RemoveIUnknown-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
dev_langs:
- C++
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b62362004f0528b16ef3dac7cbe601b8b85ce3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
  
 Standardmäßig bieten COM-Methoden virtuellen `QueryInterface`, `AddRef`, und lassen Sie die Methoden. Allerdings `ComPtr` nicht den Mehraufwand für virtuelle Methoden erfordern. `RemoveIUnknown`Dieser Aufwand durch die Bereitstellung von privaten, nicht virtuelle eliminiert `QueryInterface`, `AddRef`, und `Release` Methoden.  
  
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