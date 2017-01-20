---
title: ".CODE"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - ".CODE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".CODE directive"
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# .CODE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie mit [.MODEL](../../assembler/masm/dot-model.md)verwendet werden, gibt den Anfang eines Codesegments.  
  
## Syntax  
  
```  
.CODE [[name]]  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`name`|Optionaler Parameter, der den Namen des Codesegments angibt.  Der Standardname lautet \_TEXT für sehr klein, kleines, [Modelle](../../assembler/masm/dot-model.md)flaches und komprimiertes.  Der Standardname lautet *modulename*\_TEXT für andere Modelle.|  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)