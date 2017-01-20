---
title: "_com_error::GUID"
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
  - "GUID"
  - "_com_error.GUID"
  - "_com_error::GUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GUID-Methode"
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::GUID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft die **IErrorInfo::GetGUID**\-Funktion auf.  
  
## Syntax  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## Rückgabewert  
 Gibt das Ergebnis von **IErrorInfo::GetGUID** für das **IErrorInfo**\-Objekt zurück, das innerhalb des `_com_error`\-Objekts aufgezeichnet wird.  Wenn kein **IErrorInfo**\-Objekt erfasst wird, wird `GUID_NULL` zurückgegeben.  
  
## Hinweise  
 Jeder Fehler beim Aufrufen der **IErrorInfo::GetGUID**\-Methode wird ignoriert.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error\-Klasse](../cpp/com-error-class.md)