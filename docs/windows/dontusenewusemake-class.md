---
title: DontUseNewUseMake-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs:
- C++
helpviewer_keywords:
- DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 351b38a002c470dcd3f53e8336e393f845fdb3cf
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569568"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake-Klasse
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
class DontUseNewUseMake;  
```  
  
## <a name="remarks"></a>Hinweise  
 Verhindert die Verwendung von Operator **neue** in RuntimeClass. Folglich müssen Sie verwenden die [Funktion](../windows/make-function.md) stattdessen.  
  
## <a name="members"></a>Member  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DontUseNewUseMake::operator new-Operator](../windows/dontusenewusemake-operator-new-operator.md)|Überlädt **neue** und verhindert, dass es in RuntimeClass verwendet werden.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `DontUseNewUseMake`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [Make-Funktion](../windows/make-function.md)