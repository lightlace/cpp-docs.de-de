---
title: "ModuleBase::IncrementObjectCount-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IncrementObjectCount-Methode"
ms.assetid: 2d70b472-684c-4bb7-8bab-09505cfcaf28
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ModuleBase::IncrementObjectCount-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
virtual long IncrementObjectCount() = 0;  
```  
  
## Rückgabewert  
 Die Anzahl vor dem Inkrementieren.  
  
## Hinweise  
 Wenn Sie, Inkremente implementiert werden, die die Anzahl von Objekten vom Modul verfolgte.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [ModuleBase\-Klasse](../windows/modulebase-class.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)