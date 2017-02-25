---
title: "RuntimeClassType-Enumeration | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClassType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClassType-Enumeration"
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# RuntimeClassType-Enumeration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt den Typ von [RuntimeClass](../windows/runtimeclass-class.md)\-Instanz an, die unterstützt wird.  
  
## Syntax  
  
```  
enum RuntimeClassType;  
```  
  
## Member  
  
### Werte  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`ClassicCom`|Eine COM\-Ablaufklasse klassische.|  
|`Delegate`|Entspricht **ClassicCom**.|  
|`InhibitFtmBase`|Sperrungs `FtmBase` unterstützt, während `__WRL_CONFIGURATION_LEGACY__` nicht definiert wird.|  
|`InhibitWeakReference`|Schwache Unterstützung der Bezugs. Deaktiviert|  
|`WinRt`|Eine [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Klasse.|  
|`WinRtClassicComMix`|Eine Kombination von `WinRt` und `ClassicCom`.|  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)