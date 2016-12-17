---
title: "HandleT::Close-Methode"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close-Methode"
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT::Close-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließt das aktuelle HandleT\-Objekt.  
  
## Syntax  
  
```  
void Close();  
```  
  
## Hinweise  
 Das Handle, das dem aktuellen HandleT zugrunde liegt, ist und das HandleT Eigenschaft wird auf den ungültigen Zustand geschlossen.  
  
 Wenn das Handle nicht ordnungsgemäß schließt, wird eine Ausnahme im aufrufenden Thread ausgelöst.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HandleT\-Klasse](../windows/handlet-class.md)