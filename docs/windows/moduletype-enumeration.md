---
title: ModuleType-Enumeration | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ModuleType
dev_langs: C++
helpviewer_keywords: ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd68d911a3734510bfb35db4b3ee0c4b8e46a4a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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