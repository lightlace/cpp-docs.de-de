---
title: RuntimeClassFlags-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassFlags structure
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 823244b54513e4f6b2901bc29984604f65eb9a11
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018035"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags-Struktur
Enthält den Typ für eine Instanz von einem [RuntimeClass](../windows/runtimeclass-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
### <a name="parameters"></a>Parameter  
 *flags*  
 Ein [RuntimeClassType-Enumeration](../windows/runtimeclasstype-enumeration.md) Wert.  
  
## <a name="members"></a>Member  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[RuntimeClassFlags::value-Konstante](../windows/runtimeclassflags-value-constant.md)|Enthält eine [RuntimeClassType-Enumeration](../windows/runtimeclasstype-enumeration.md) Wert.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `RuntimeClassFlags`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)