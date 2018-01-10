---
title: InterfaceList-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceList
dev_langs: C++
helpviewer_keywords: InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: def0a79556d74616d153a97ee5a0cc9f521944ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="interfacelist-structure"></a>InterfaceList-Struktur
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename T,  
   typename U  
>  
struct InterfaceList;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Einen Schnittstellennamen; die erste Schnittstelle in der Liste rekursiv.  
  
 `U`  
 Einen Schnittstellennamen; die verbleibenden Schnittstellen in der Liste rekursiv.  
  
## <a name="remarks"></a>Hinweise  
 So erstellen eine rekursive Liste von Schnittstellen verwendet.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`FirstT`|Synonym für den Vorlagenparameter `T`.|  
|`RestT`|Synonym für den Vorlagenparameter `U`.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `InterfaceList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)