---
title: "_com_error::WCodeToHRESULT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::WCodeToHRESULT"
  - "_com_error.WCodeToHRESULT"
  - "WCodeToHRESULT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WCodeToHRESULT-Methode"
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::WCodeToHRESULT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ordnet 16\-Bit\-`wCode` dem 32\-Bit\-`HRESULT` zu.  
  
## Syntax  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### Parameter  
 `wCode`  
 Der 16\-Bit\-`HRESULT`, der dem 32\-Bit\-`wCode` zugeordnet werden soll.  
  
## Rückgabewert  
 32\-Bit\-`HRESULT`, der vom 16\-Bit\- `wCode` zugeordnet wurde.  
  
## Hinweise  
 Weitere Informationen erhalten Sie unter der [WCode](../cpp/com-error-wcode.md)\-Memberfunktion.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error::WCode](../cpp/com-error-wcode.md)   
 [\_com\_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [\_com\_error\-Klasse](../cpp/com-error-class.md)