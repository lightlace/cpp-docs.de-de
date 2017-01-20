---
title: "_com_error::ErrorInfo"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::ErrorInfo"
  - "ErrorInfo"
  - "_com_error.ErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorInfo-Methode"
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::ErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft das **IErrorInfo**\-Objekt ab, das an den Konstruktor übergeben wurde.  
  
## Syntax  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## Rückgabewert  
 Unformatiertes **IErrorInfo**\-Element, das an den Konstruktor übergeben wurde.  
  
## Hinweise  
 Ruft das gekapselte **IErrorInfo**\-Element in einem `_com_error`\-Objekt oder **NULL** ab, wenn kein **IErrorInfo**\-Element erfasst ist.  Der Aufrufer muss nach der Verwendung für das zurückgegebene Objekt **Release** aufrufen.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error\-Klasse](../cpp/com-error-class.md)