---
title: "MakeAllocator::Detach-Methode"
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
  - "implements/Microsoft::WRL::Details::MakeAllocator::Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach-Methode"
ms.assetid: 78012634-2dda-4ea2-9ffe-40f105d2fe47
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# MakeAllocator::Detach-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
__forceinline void Detach();  
```  
  
## Hinweise  
 Hebt des Arbeitsspeichers die Zuordnung durch die [Zuordnen zu](../windows/makeallocator-allocate-method.md)\-Methode vom aktuellen MakeAllocator\-Objekt zugeordnet ist.  
  
 Wenn Sie Detach\(\)aufrufen, können Sie zum Löschen des Arbeitsspeichers verantwortlich, der auf die Zuordnensart bereitgestellt wird.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [MakeAllocator\-Klasse](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)