---
title: ArgTraitsHelper-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs:
- C++
helpviewer_keywords:
- ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4df7e9fe3823e3dbb84b09863e6de5178ab44d18
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper-Struktur
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename TDelegateInterface>  
struct ArgTraitsHelper;  
```  
  
#### <a name="parameters"></a>Parameter  
 `TDelegateInterface`  
 Ein Delegat-Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Unterstützt definiert allgemeine Merkmale Delegatargumente.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`methodType`|Ein Synonym für `decltype(&TDelegateInterface::Invoke)`.|  
|`Traits`|Ein Synonym für `ArgTraits<methodType>`.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[ArgTraitsHelper::args-Konstante](../windows/argtraitshelper-args-constant.md)|Hilft [argtraits:: args](../windows/argtraits-args-constant.md) die Anzahl von Parametern für die Invoke-Methode einer Schnittstelle Delegaten beibehalten.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ArgTraitsHelper`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)