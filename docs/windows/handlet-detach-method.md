---
title: "HandleT::Detach-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach-Methode"
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HandleT::Detach-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Hebt des aktuellen HandleT\-Objekts von seinem zugrunde liegenden Handle die Zuordnung.  
  
## Syntax  
  
```  
typename HandleTraits::Type Detach();  
```  
  
## Rückgabewert  
 Das zugrunde liegenden Handles.  
  
## Hinweise  
 Wenn dieser Vorgang abgeschlossen hat, wird das aktuelle HandleT auf den ungültigen Zustand festgelegt.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HandleT\-Klasse](../windows/handlet-class.md)