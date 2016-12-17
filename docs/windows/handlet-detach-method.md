---
title: "HandleT::Detach-Methode"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach-Methode"
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
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