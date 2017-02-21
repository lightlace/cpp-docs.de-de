---
title: "HandleT::Close-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close-Methode"
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
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