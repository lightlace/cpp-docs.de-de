---
title: "RoInitializeWrapper::RoInitializeWrapper-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper"
dev_langs: 
  - "C++"
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
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