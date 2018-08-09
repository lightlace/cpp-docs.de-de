---
title: RuntimeClassType-Enumeration | Microsoft-Dokumentation
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
ms.openlocfilehash: 1b54813a41a8857e4533f21d1eb0adaf8dcecd25
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010820"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType-Enumeration
Gibt den Typ der [RuntimeClass](../windows/runtimeclass-class.md) -Instanz, die unterstützt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>Member  
  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`ClassicCom`|Eine klassische COM-Runtime-Klasse.|  
|`Delegate`|Entspricht `ClassicCom`.|  
|`InhibitFtmBase`|Deaktiviert die `FtmBase` -Unterstützung während der `__WRL_CONFIGURATION_LEGACY__` ist nicht definiert.|  
|`InhibitWeakReference`|Deaktiviert die Unterstützung von schwachen Verweis.|  
|`WinRt`|Eine Windows-Runtime-Klasse.|  
|`WinRtClassicComMix`|Die Kombination aus `WinRt` und `ClassicCom`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)