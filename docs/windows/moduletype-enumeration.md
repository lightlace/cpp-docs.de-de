---
title: "ModuleType-Enumeration"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ModuleType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ModuleType-Enumeration"
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ModuleType-Enumeration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob ein Modul einem prozessinternen Server oder einen prozessexternen Server unterstützen soll.  
  
## Syntax  
  
```  
enum ModuleType;  
```  
  
## Member  
  
### Werte  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`InProc`|Ein prozessinterner Server.|  
|`OutOfProc`|Ein prozessexterner Server.|  
|`DisableCaching`|Sperrungszwischenspeichernmechanismus Modul auf.|  
|`InProcDisableCaching`|Kombination von `InProc` und `DisableCaching`.|  
|`OutOfProcDisableCaching`|Kombination von `OutOfProc` und `DisableCaching`.|  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)