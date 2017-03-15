---
title: "MakeAllocator::Allocate-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::MakeAllocator::Allocate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Allocate-Methode"
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
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