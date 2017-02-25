---
title: "ModuleType-Enumeration | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ModuleType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ModuleType-Enumeration"
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
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