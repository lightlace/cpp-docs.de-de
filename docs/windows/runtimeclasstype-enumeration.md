---
title: RuntimeClassType-Enumeration | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClassType
dev_langs: C++
helpviewer_keywords: RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 26016e8c95807af76484504c491ca1e6e08f8f96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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