---
title: "RoInitializeWrapper::RoInitializeWrapper-Konstruktor"
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
  - "corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper"
dev_langs: 
  - "C++"
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# RoInitializeWrapper::RoInitializeWrapper-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine neue Instanz der RoInitializeWrapper\-Klasse.  
  
## Syntax  
  
```cpp  
RoInitializeWrapper(  
   RO_INIT_TYPE flags)  
  
```  
  
#### Parameter  
 `flags`  
 Eine der RO\_INIT\_TYPE\-Enumerationen, die der Unterstützung angibt, wurde von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## Hinweise  
 Die RoInitializeWrapper\-Klasse ruft Windows::Foundation::Initialize auf \(*flags*\).  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HandleT\-Klasse](../windows/handlet-class.md)