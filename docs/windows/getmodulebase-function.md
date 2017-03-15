---
title: "GetModuleBase-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::GetModuleBase"
dev_langs: 
  - "C++"
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# GetModuleBase-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft einen Zeiger [ModuleBase](../windows/modulebase-class.md) ab, der das Erhöhen und Verringern des Verweiszählers [RuntimeClass](../windows/runtimeclass-class.md) eines Objekts ermöglicht.  
  
## Syntax  
  
```cpp  
inline Details::ModuleBase* GetModuleBase() throw()  
```  
  
## Rückgabewert  
 Ein Zeiger auf ein `ModuleBase`\-Objekt.  
  
## Hinweise  
 Diese Funktion wird intern verwendet, um Objektverweisanzahlen zu inkrementieren und zu dekrementieren.  
  
 Sie können diese Funktion verwenden, um von Verweiszählern zu steuern, indem Sie [ModuleBase::IncrementObjectCount](../windows/modulebase-incrementobjectcount-method.md) und [ModuleBase::DecrementObjectCount](../windows/modulebase-decrementobjectcount-method.md) aufgerufen werden.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)