---
title: RuntimeClassType-Enumeration | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 43ab0a738af4c6bc92d42c0884827b574946d2ea
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType-Enumeration
Gibt den Typ des [RuntimeClass](../windows/runtimeclass-class.md) -Instanz, die unterstützt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>Member  
  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`ClassicCom`|Eine klassische COM-Runtime-Klasse.|  
|`Delegate`|Entspricht **ClassicCom**.|  
|`InhibitFtmBase`|Deaktiviert die `FtmBase` Unterstützung beim `__WRL_CONFIGURATION_LEGACY__` ist nicht definiert.|  
|`InhibitWeakReference`|Deaktiviert die Unterstützung von schwachen Verweis.|  
|`WinRt`|Eine Windows-Runtime-Klasse.|  
|`WinRtClassicComMix`|Die Kombination aus `WinRt` und `ClassicCom`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)