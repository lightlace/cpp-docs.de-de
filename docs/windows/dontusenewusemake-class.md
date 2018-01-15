---
title: DontUseNewUseMake-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs: C++
helpviewer_keywords: DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c09276fb761dcd1f2f5be78afa40606e262aa3e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake-Klasse
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
class DontUseNewUseMake;  
```  
  
## <a name="remarks"></a>Hinweise  
 Verhindert die Verwendung von Operator `new` in RuntimeClass. Folglich müssen Sie verwenden die [Make-Funktion](../windows/make-function.md) stattdessen.  
  
## <a name="members"></a>Member  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DontUseNewUseMake::operator new-Operator](../windows/dontusenewusemake-operator-new-operator.md)|Überlädt `new` und verhindert, dass er im RuntimeClass verwendet werden.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `DontUseNewUseMake`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [Make-Funktion](../windows/make-function.md)