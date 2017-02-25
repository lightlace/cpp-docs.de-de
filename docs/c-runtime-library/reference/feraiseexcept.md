---
title: "feraiseexcept | Microsoft Docs"
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
  - "feraiseexcept"
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
apitype: "HeaderDef"
f1_keywords: 
  - "feraiseexcept"
  - "fenv/feraiseexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Feraiseexcept-Funktion"
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# feraiseexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Löst den angegebenen Ausnahmen aus.  
  
## Syntax  
  
```  
int feraiseexcept(  
   int excepts  
);  
```  
  
#### Parameter  
 `excepts`  
 Die Ausnahmen auslösen.  
  
## Rückgabewert  
 Wenn alle angegebene Ausnahmen erfolgreich ausgelöst werden, wird 0 zurückgegeben.  
  
## Hinweise  
 Die `feraiseexcept` \-Funktion versucht, den angegebenen Ausnahmen auslösen `excepts`.   Die `feraiseexcept` \-Funktion unterstützt diese Ausnahmemakros in \< fenv.h \> definiert:  
  
|Ausnahme\-Makro|Beschreibung|  
|---------------------|------------------|  
|FE\_DIVBYZERO|Eine Singularität oder pol Fehler in einer zuvor Gleitkommaoperation; ein Unendlichkeitswert erstellt wurde.|  
|FE\_INEXACT|Die Funktion wurde erzwungen, das gespeicherte Ergebnis einer zuvor Gleitkommaoperation gerundet.|  
|FE\_INVALID|Domänenfehler in einer zuvor Gleitkommaoperation.|  
|FE\_OVERFLOW|Ein Fehler aufgetreten. eine frühere Gleitkommaoperation Ergebnis war zu groß dargestellt werden soll.|  
|FE\_UNDERFLOW|Eine frühere Gleitkommaoperation Ergebnis war zu klein für die bei voller Genauigkeit dargestellt werden; ein Denormal\-Wert wurde erstellt.|  
|FE\_ALLEXCEPT|Der bitweise OR aller unterstützt Gleitkommaausnahmen.|  
  
 Die `excepts` Argument NULL ist, werden möglicherweise einer Ausnahme Makrowerte oder das bitweise oder der zwei oder mehr der unterstützten Ausnahmemakros. Wenn eines der angegebenen Ausnahmemakros FE\_OVERFLOW oder FE\_UNDERFLOW ist, kann als Nebeneffekt die FE\_INEXACT\-Ausnahme ausgelöst.  
  
 Um diese Funktion verwenden zu können, müssen Sie wieder deaktivieren Gleitkomma Optimierungen, die Zugriff mithilfe von verhindern könnten die `#pragma fenv_access(on)` Richtlinie vor dem Aufruf. Weitere Informationen finden Sie unter [fenv\_access](../../preprocessor/fenv-access.md).  
  
 **Microsoft Specific:** die Ausnahmen, die im angegebenen `excepts` ausgelöst werden, in der Reihenfolge FE\_INVALID, FE\_DIVBYZERO, FE\_OVERFLOW, FE\_UNDERFLOW, FE\_INEXACT. Allerdings FE\_INEXACT können werden ausgelöst, wenn FE\_OVERFLOW oder FE\_UNDERFLOW ausgelöst, auch wenn nicht im angegebenen `excepts`.**Ende Microsoft\-spezifisch**  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`feraiseexcept`|\<fenv.h\>|\<cfenv\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)