---
title: "AsyncResultType-Enumeration | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncResultType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncResultType-Enumeration"
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncResultType-Enumeration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt den Typ des Ergebnisses zurückgegeben durch die GetResults\(\) Methode an.  
  
## Syntax  
  
```  
enum AsyncResultType;  
```  
  
## Member  
  
### Werte  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`MultipleResults`|Ein Satz, die mehrere Ergebnisse progressiv zwischen Anfangszustand dargestellt werden und bevor Close\(\) aufgerufen wird.|  
|`SingleResult`|Ein einzelnes Ergebnis, das angezeigt wird, nachdem das vollständige Ereignis auftritt.|  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)