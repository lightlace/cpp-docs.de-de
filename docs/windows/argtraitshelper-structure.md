---
title: ArgTraitsHelper-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs: C++
helpviewer_keywords: ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31d9072ebf8c36453a74c75ff4a8997805d0973f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper-Struktur
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   typename TDelegateInterface  
>  
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