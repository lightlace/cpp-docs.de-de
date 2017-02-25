---
title: "fesetenv1 | Microsoft Docs"
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
  - "fesetenv"
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
  - "fesetenv"
  - "fenv/fesetenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fesetenv-Funktion"
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# fesetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die aktuelle Gleitkomma\-Umgebung.  
  
## Syntax  
  
```  
int fesetenv(  
   const fenv_t *penv  
);  
  
```  
  
#### Parameter  
 `penv`  
 Zeiger auf ein `fenv_t` Objekt, das eine Gleitkommazahl Umgebung festgelegt durch einen Aufruf von enthält [fegetenv](../Topic/fegetenv2.md) oder [feholdexcept](../Topic/feholdexcept1.md). Sie können auch Standard Gleitkomma Autostart angeben, indem Sie das FE\_DFL\_ENV\-Makro.  
  
## Rückgabewert  
 Gibt 0 zurück, wenn die Umgebung erfolgreich festgelegt wurde. Andernfalls wird einen Wert ungleich NULL zurückgegeben.  
  
## Hinweise  
 Die `fesetenv` Funktion legt die aktuelle Gleitkomma\-Umgebung aus der in gespeicherte Wert dem `fenv_t` Objekt verweist `penv`. Die floating Point\-Umgebung ist ein Satz von Status\-Flags und Steuerelement\-Modi, die gleitkommaberechnungen beeinflussen. Dies schließt das Rundungsverhalten und die Statusflags für Gleitkommaausnahmen. Wenn `penv` nicht FE\_DFL\_ENV oder verweist nicht auf eine gültige `fenv_t` \-Objekt nachfolgendes Verhalten ist nicht definiert.  
  
 Ein Aufruf dieser Funktion legt die Ausnahme Status\-Flags, die in der `penv` \-Objekt löst keine Ausnahmen.  
  
 Um diese Funktion verwenden zu können, müssen Sie wieder deaktivieren Gleitkomma Optimierungen, die Zugriff mithilfe von verhindern könnten die `#pragma fenv_access(on)` Richtlinie vor dem Aufruf. Weitere Informationen finden Sie unter [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`fesetenv`|\<fenv.h\>|\<cfenv\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)