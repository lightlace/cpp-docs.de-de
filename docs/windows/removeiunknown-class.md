---
title: "RemoveIUnknown-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::RemoveIUnknown"
dev_langs: 
  - "C++"
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# RemoveIUnknown-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
#### Parameter  
 `T`  
 Eine Klasse.  
  
## Hinweise  
 Macht einen Typ, der zu einem `IUnknown`\- Typ entspricht, jedoch hat nicht virtuelles `QueryInterface`, `AddRef` und `Release`\-Memberfunktionen.  
  
 Standardmäßig stellen COM\-Methoden virtuelles `QueryInterface`, `AddRef` und Versionsmethoden.  Für `ComPtr` nicht den Mehraufwand von Methoden.  `RemoveIUnknown` überflüssig diesen Mehraufwand, indem privates, nicht virtuelles `QueryInterface`, `AddRef` und `Release` für Methoden bereitstellt.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`ReturnType`|Ein Synonym für einen Typ, der an den Vorlagenparameter `T` entspricht, nicht virtuelle IUnknown\-Member hat.|  
  
## Vererbungshierarchie  
 `T`  
  
 `RemoveIUnknown`  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)