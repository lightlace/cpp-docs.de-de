---
title: InterfaceList-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
dev_langs:
- C++
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 318738e5f4ac623987b1002e5204739407adcdb9
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017757"
---
# <a name="interfacelist-structure"></a>InterfaceList-Struktur
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <  
   typename T,  
   typename U  
>  
struct InterfaceList;  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Der Schnittstellenname einer; die erste Schnittstelle in der Liste rekursiv.  
  
 *U*  
 Der Schnittstellenname einer; die verbleibenden Schnittstellen in der Liste rekursiv.  
  
## <a name="remarks"></a>Hinweise  
 Verwendet, um eine rekursive Liste von Schnittstellen erstellen.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`FirstT`|Synonym für den Vorlagenparameter *T*.|  
|`RestT`|Synonym für den Vorlagenparameter *U*.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `InterfaceList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)