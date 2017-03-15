---
title: "_com_error::HelpContext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::HelpContext"
  - "HelpContext"
  - "_com_error.HelpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HelpContext-Methode"
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::HelpContext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft die **IErrorInfo::GetHelpContext**\-Funktion auf.  
  
## Syntax  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## Rückgabewert  
 Gibt das Ergebnis von **IErrorInfo::GetHelpContext** für das **IErrorInfo**\-Objekt zurück, das innerhalb des `_com_error`\-Objekts erfasst wird.  Wenn kein **IErrorInfo**\-Objekt erfasst wird, wird 0 zurückgegeben.  
  
## Hinweise  
 Jeder Fehler beim Aufrufen der **IErrorInfo::GetHelpContext**\-Methode wird ignoriert.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error\-Klasse](../cpp/com-error-class.md)