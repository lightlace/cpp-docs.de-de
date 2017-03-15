---
title: "AsyncBase::FireProgress-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::FireProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FireProgress-Methode"
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::FireProgress-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den aktuellen Statusereignishandler auf.  
  
## Syntax  
  
```  
void FireProgress(  
   const typename ProgressTraits::Arg2Type arg  
);  
```  
  
#### Parameter  
 `arg`  
 Die aufzurufen Ereignishandlermethode.  
  
## Hinweise  
 `ProgressTraits` ist von [ArgTraitsHelper\-Struktur](../windows/argtraitshelper-structure.md) abgeleitet.  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [AsyncBase\-Klasse](../windows/asyncbase-class.md)