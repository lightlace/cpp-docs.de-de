---
title: "_com_error::Source"
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
  - "_com_error.Source"
  - "_com_error::Source"
  - "source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Quellmethode"
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::Source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft die **IErrorInfo::GetSource**\-Funktion auf.  
  
## Syntax  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## Rückgabewert  
 Gibt das Ergebnis von **IErrorInfo::GetSource** für das **IErrorInfo**\-Objekt zurück, das innerhalb des `_com_error`\-Objekts aufgezeichnet wird.  Das resultierende BSTR wird in einem `_bstr_t`\-Objekt gekapselt.  Wenn kein **IErrorInfo** erfasst wird, wird eine leere `_bstr_t` zurückgegeben.  
  
## Hinweise  
 Jeder Fehler beim Aufrufen der **IErrorInfo::GetSource**\-Methode wird ignoriert.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error\-Klasse](../cpp/com-error-class.md)