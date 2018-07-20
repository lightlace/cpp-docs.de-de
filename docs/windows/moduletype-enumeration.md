---
title: ModuleType-Enumeration | Microsoft Docs
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
ms.openlocfilehash: d36355c9f64f9f5c827ef8c4d5b3cb6a77d17b65
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876835"
---
# <a name="moduletype-enumeration"></a>ModuleType-Enumeration
Gibt an, ob ein Modul einen In-Process-Server oder einen Out-of-Process-Server unterstützen sollte.   
  
## <a name="syntax"></a>Syntax  
  
```  
enum ModuleType;  
```  
  
## <a name="members"></a>Member  
  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`InProc`|In-Process-Server.|  
|`OutOfProc`|Ein Out-of-Process-Server.|  
|`DisableCaching`|Deaktivieren Sie Zwischenspeichermechanismus für Modul an.|  
|`InProcDisableCaching`|Kombination von `InProc` und `DisableCaching`.|  
|`OutOfProcDisableCaching`|Kombination von `OutOfProc` und `DisableCaching`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)