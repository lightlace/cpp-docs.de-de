---
title: "InspectableClass-Makro"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::InspectableClass"
dev_langs: 
  - "C++"
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# InspectableClass-Makro
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt den Ablaufklassennamen und die Vertrauensebene fest.  
  
## Syntax  
  
```cpp  
  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
  
```  
  
#### Parameter  
 `runtimeClassName`  
 Der vollständige wörtliche Name der Laufzeitklasse.  
  
 `trustLevel`  
 Einer der [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx)\-Enumerationswerte.  
  
## Hinweise  
 Das `InspectableClass`\-Makro kann nur mit [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Typen verwendet werden.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [RuntimeClass\-Klasse](../windows/runtimeclass-class.md)