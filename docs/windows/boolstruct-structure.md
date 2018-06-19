---
title: BoolStruct-Struktur | Microsoft Docs
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
ms.openlocfilehash: af2827d85a1df647dca2c02c5c6ee5a12a416d51
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860121"
---
# <a name="boolstruct-structure"></a>BoolStruct-Struktur
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct BoolStruct;  
```  
  
## <a name="remarks"></a>Hinweise  
 BoolStruct-Struktur definiert, ob ein comptr-Objekt die Objektlebensdauer einer Schnittstelle verwaltet wird. BoolStruct wird intern von verwendet die [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) Operator.  
  
## <a name="members"></a>Member  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[BoolStruct::Member-Datenmember](../windows/boolstruct-member-data-member.md)|Gibt an, dass eine [ComPtr](../windows/comptr-class.md) ist, oder verwalten die Objektlebensdauer einer Schnittstelle nicht der Fall ist.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `BoolStruct`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtr::operator Microsoft::WRL::Details::BoolType-Operator](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)