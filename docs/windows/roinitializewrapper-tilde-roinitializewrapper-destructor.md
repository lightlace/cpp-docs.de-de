---
title: "RoInitializeWrapper::~RoInitializeWrapper-Destruktor"
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
  - "corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper"
dev_langs: 
  - "C++"
ms.assetid: afef4c1f-ffde-4cd2-8654-8de4182eb5f4
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# RoInitializeWrapper::~RoInitializeWrapper-Destruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deinitialisiert [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## Syntax  
  
```cpp  
~RoInitializeWrapper()  
```  
  
## Hinweise  
 Die RoInitializeWrapper\-Klasse ruft Windows::Foundation::Uninitialize\(\)auf.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HandleT\-Klasse](../windows/handlet-class.md)