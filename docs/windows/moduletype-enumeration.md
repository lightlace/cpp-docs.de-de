---
title: ModuleType-Enumeration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
dev_langs:
- C++
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 831f1fbcb2da205fa08286a1fbbbf414e66075d4
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019929"
---
# <a name="moduletype-enumeration"></a>ModuleType-Enumeration
Gibt an, ob ein Modul einen In-Process-Server oder einen Out-of-Process-Server unterstützen sollte.   
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum ModuleType;  
```  
  
## <a name="members"></a>Member  
  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`InProc`|In-Process-Server.|  
|`OutOfProc`|Ein Out-of-Process-Server.|  
|`DisableCaching`|Deaktivieren Sie Zwischenspeichermechanismus Modul.|  
|`InProcDisableCaching`|Kombination von `InProc` und `DisableCaching`.|  
|`OutOfProcDisableCaching`|Kombination von `OutOfProc` und `DisableCaching`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)