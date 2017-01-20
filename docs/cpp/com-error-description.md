---
title: "_com_error::Description"
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
  - "_com_error.Description"
  - "_com_error::Description"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Description-Methode"
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::Description
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft die **IErrorInfo::GetDescription**\-Funktion auf.  
  
## Syntax  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## Rückgabewert  
 Gibt das Ergebnis von **IErrorInfo::GetDescription** für das **IErrorInfo**\-Objekt zurück, das innerhalb des `_com_error`\-Objekts aufgezeichnet wird.  Das resultierende `BSTR` wird in einem `_bstr_t`\-Objekt gekapselt.  Wenn kein **IErrorInfo** erfasst wird, wird eine leere `_bstr_t` zurückgegeben.  
  
## Hinweise  
 Ruft die **IErrorInfo::GetDescription** \-Funktion auf und ruft **IErrorInfo** ab, das innerhalb des `_com_error`\-Objekts aufgezeichnet wird.  Jeder Fehler beim Aufrufen der **IErrorInfo::GetDescription**\-Methode wird ignoriert.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error\-Klasse](../cpp/com-error-class.md)