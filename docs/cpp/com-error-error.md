---
title: "_com_error::Error | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error.Error"
  - "_com_error::Error"
  - "Error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Error-Methode"
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::Error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft das an den Konstruktor übergebene `HRESULT` ab.  
  
## Syntax  
  
```  
  
HRESULT Error( ) const throw( );  
  
```  
  
## Rückgabewert  
 Unformatiertes `HRESULT`\-Element, das an den Konstruktor übergeben wird.  
  
## Hinweise  
 Ruft das gekapselte `HRESULT`\-Element in einem `_com_error`\-Objekt ab.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error\-Klasse](../cpp/com-error-class.md)