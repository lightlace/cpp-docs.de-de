---
title: BoolStruct-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
dev_langs:
- C++
helpviewer_keywords:
- BoolStruct structure
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14e3d81ca273bf96b4812f08a46904c9d521c5cf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650481"
---
# <a name="boolstruct-structure"></a>BoolStruct-Struktur
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
struct BoolStruct;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **BoolStruct** Struktur definiert, ob eine `ComPtr` die Objektlebensdauer einer Schnittstelle verwaltet. **BoolStruct** werden intern von der [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) Operator.  
  
## <a name="members"></a>Member  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[BoolStruct::Member-Datenmember](../windows/boolstruct-member-data-member.md)|Gibt an, dass eine [ComPtr](../windows/comptr-class.md) ist, oder ist nicht der Fall, die Objektlebensdauer einer Schnittstelle verwalten.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `BoolStruct`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtr::operator Microsoft::WRL::Details::BoolType-Operator](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)