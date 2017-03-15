---
title: "_com_error::HelpFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "HelpFile"
  - "_com_error::HelpFile"
  - "_com_error.HelpFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HelpFile-Methode"
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::HelpFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft die **IErrorInfo::GetHelpFile**\-Funktion auf.  
  
## Syntax  
  
```  
  
_bstr_t HelpFile() const;  
  
```  
  
## Rückgabewert  
 Gibt das Ergebnis von **IErrorInfo::GetHelpFile** für das **IErrorInfo**\-Objekt zurück, das innerhalb des `_com_error`\-Objekts aufgezeichnet wird.  Das resultierende BSTR wird in einem `_bstr_t`\-Objekt gekapselt.  Wenn kein **IErrorInfo** erfasst wird, wird eine leere `_bstr_t` zurückgegeben.  
  
## Hinweise  
 Jeder Fehler beim Aufrufen der **IErrorInfo::GetHelpFile**\-Methode wird ignoriert.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error\-Klasse](../cpp/com-error-class.md)