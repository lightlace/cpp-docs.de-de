---
title: "fegetenv1 | Microsoft Docs"
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
  - "fetegenv"
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
  - "fegetenv"
  - "fenv/fegetenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fetegenv-Funktion"
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# fegetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Speichert die aktuelle Gleitkomma\-Umgebung in das angegebene Objekt.  
  
## Syntax  
  
```  
int fegetenv(  
   fenv_t *penv  
);  
  
```  
  
#### Parameter  
 `penv`  
 Zeiger auf ein `fenv_t` Objekt, das die aktuellen Umgebungswerte der Gleitkomma\-enthalten.  
  
## Rückgabewert  
 Gibt 0, wenn die Gleitkomma\-Umgebung erfolgreich gespeichert wurde `penv`. Andernfalls wird einen Wert ungleich NULL zurückgegeben.  
  
## Hinweise  
 Die `fegetenv` Funktion speichert die aktuelle Gleitkomma\-Umgebung in das Objekt, das auf `penv`. Die floating Point\-Umgebung ist ein Satz von Status\-Flags und Steuerelement\-Modi, die gleitkommaberechnungen beeinflussen. Dies schließt das Rundungsverhalten Richtung und den Status\-Flags für Gleitkommaausnahmen. Wenn `penv` verweist nicht auf eine gültige `fenv_t` \-Objekt nachfolgendes Verhalten ist nicht definiert.  
  
 Um diese Funktion verwenden zu können, müssen Sie wieder deaktivieren Gleitkomma Optimierungen, die Zugriff mithilfe von verhindern könnten die `#pragma fenv_access(on)` Richtlinie vor dem Aufruf. Weitere Informationen finden Sie unter [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`fegetenv`|\<fenv.h\>|\<cfenv\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetenv](../../c-runtime-library/reference/fesetenv1.md)