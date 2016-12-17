---
title: "MakeAllocator::Allocate-Methode"
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
  - "implements/Microsoft::WRL::Details::MakeAllocator::Allocate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Allocate-Methode"
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# MakeAllocator::Allocate-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
__forceinline void* Allocate();  
```  
  
## Rückgabewert  
 Wenn erfolgreich, ein Zeiger auf den reservierten Speicher; andernfalls `nullptr`.  
  
## Hinweise  
 Belegt Speicher und ordnet ihn dem aktuellen MakeAllocator\-Objekt zu.  
  
 Die Größe des reservierten Arbeitsspeicher ist die Größe des Typs, der durch den aktuellen MakeAllocator\-Vorlagenparameter angegeben wird.  
  
 Ein Entwickler muss nur die Allocate\(\) Methode überschreiben, um ein anderes Speicherbelegungsmodell zu implementieren.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [MakeAllocator\-Klasse](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)