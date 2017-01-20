---
title: "Ausnahmen (C/C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ERROR_MOD_NOT_FOUND"
  - "vcppException"
  - "ERROR_SEVERITY_ERROR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++-Ausnahmebehandlung, Verzögertes Laden von DLLs"
  - "Verzögertes Laden von DLLs, Ausnahmen"
  - "ERROR_MOD_NOT_FOUND-Ausnahme"
  - "ERROR_SEVERITY_ERROR-Ausnahme"
  - "vcppException"
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Ausnahmen (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es gibt zwei Ausnahmecodes, die beim Auftreten von Fehlern ausgelöst werden können:  
  
-   ein Ausnahmecode für einen **LoadLibrary**\-Fehler.  
  
-   ein Ausnahmecode für einen **GetProcAddress**\-Fehler.  
  
 Die Ausnahmeinformationen sehen wie folgt aus:  
  
```  
//  
// Exception information  
//  
#define FACILITY_VISUALCPP  ((LONG)0x6d)  
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)  
```  
  
 Bei den ausgelösten Ausnahmecodes handelt es sich um die Standardwerte **VcppException\(ERROR\_SEVERITY\_ERROR, ERROR\_MOD\_NOT\_FOUND\)** und **VcppException\(ERROR\_SEVERITY\_ERROR, ERROR\_PROC\_NOT\_FOUND\)**.  Von der Ausnahme wird ein Zeiger auf eine **DelayLoadInfo**\-Struktur im LPDWORD\-Wert übergeben. Dieser Wert kann von **GetExceptionInformation** im Feld ExceptionInformation\[0\] der [EXCEPTION\_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082)\-Struktur abgerufen werden.  
  
 Wenn die falschen Bits im **grAttrs**\-Feld festgelegt sind, wird zusätzlich die `ERROR_INVALID_PARAMETER`\-Ausnahme ausgelöst.  Diese Ausnahme ist in jedem Fall schwerwiegend.  
  
 Weitere Informationen finden Sie unter [Struktur\- und Konstantendefinitionen](../../build/reference/structure-and-constant-definitions.md).  
  
## Siehe auch  
 [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md)