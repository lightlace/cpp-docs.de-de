---
title: "_com_error::HRESULTToWCode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "HRESULTToWCode"
  - "_com_error.HRESULTToWCode"
  - "_com_error::HRESULTToWCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HRESULTToWCode-Methode"
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::HRESULTToWCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ordnet 32\-Bit\-`HRESULT` dem 16\-Bit\-`wCode` zu.  
  
## Syntax  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### Parameter  
 `hr`  
 Das 32\-Bit\-`HRESULT`, das dem 16\-Bit\- `wCode` zugeordnet werden soll.  
  
## Rückgabewert  
 16\-Bit\-`wCode`, der vom 32\-Bit\- `HRESULT` zugeordnet wurde.  
  
## Hinweise  
 Weitere Informationen erhalten Sie unter [\_com\_error::WCode](../cpp/com-error-wcode.md).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error::WCode](../cpp/com-error-wcode.md)   
 [\_com\_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [\_com\_error\-Klasse](../cpp/com-error-class.md)