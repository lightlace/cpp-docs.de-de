---
title: "feholdexcept2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "feholdexcept"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "feholdexcept"
  - "fenv/feholdexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Feholdexcept-Funktion"
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# feholdexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Speichert die aktuelle Gleitkomma\-Umgebung in das angegebene Objekt, löscht der Gleitkomma Statusflags und, wenn möglich, gleitkommaumgebung Nonstop\-Modus versetzt.  
  
## Syntax  
  
```  
int feholdexcept(  
   fenv_t *penv  
);  
  
```  
  
#### Parameter  
 `penv`  
 Zeiger auf ein `fenv_t` Objekt, das eine Kopie der Gleitkomma\-Umgebung enthalten.  
  
## Rückgabewert  
 Gibt 0 \(null\) zurück, wenn die Funktion erfolgreich ununterbrochenen Gleitkommaausnahmen behandeln aktivieren kann.  
  
## Hinweise  
 Die `feholdexcept` Funktion wird verwendet, um den Zustand der aktuellen floating Point\-Umgebung im Speichern der `fenv_t` Objekt verweist `penv`, und die Umgebung nicht unterbrechen der Ausführung auf Gleitkommaausnahmen festlegen. Dies wird als Nonstop\-Modus bezeichnet.  Dieser Modus wird fortgesetzt, bis zur Wiederherstellung der umgebungs mit [Fesetenv](../Topic/fesetenv2.md) oder [feupdateenv](../../c-runtime-library/reference/feupdateenv.md).  
  
 Am Anfang eine Unterroutine, die eine oder mehrere Ausnahmen vom Aufrufer ausblenden muss, können Sie diese Funktion verwenden. Um eine Ausnahme zu melden, löschen Sie einfach die unerwünschten Ausnahmen mit [Feclearexcept,](../../c-runtime-library/reference/feclearexcept1.md) und beenden Sie dann den ununterbrochenen\-Modus mit einem Aufruf von `feupdateenv`.  
  
 Um diese Funktion verwenden zu können, müssen Sie wieder deaktivieren Gleitkomma Optimierungen, die Zugriff mithilfe von verhindern könnten die `#pragma fenv_access(on)` Richtlinie vor dem Aufruf. Weitere Informationen finden Sie unter [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`feholdexcept`|\<fenv.h\>|\<cfenv\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [fesetenv](../Topic/fesetenv2.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)