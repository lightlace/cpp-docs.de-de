---
title: "fesetexceptflag2 | Microsoft Docs"
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
  - "fesetexceptflag"
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
  - "fesetexceptflag"
  - "fenv/fesetexceptflag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fesetexceptflag-Funktion"
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# fesetexceptflag
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die angegebenen Gleitkomma\-Status\-Flags in der aktuellen Gleitkomma\-Umgebung.  
  
## Syntax  
  
```  
int fesetexceptflag(  
     const fexcept_t *pstatus,  
     int excepts  
);  
  
```  
  
#### Parameter  
 `pstatus`  
 Zeiger auf ein  `fexcept_t` Objekt, das die Werte der Ausnahme Status\-Flags festgelegt werden soll. Das Objekt kann festgelegt werden, durch einen vorherigen Aufruf von [fegetexceptflag](../Topic/fegetexceptflag1.md).  
  
 `excepts`  
 Gleitkommaausnahmen Status\-Flags festgelegt.  
  
## Rückgabewert  
 Wenn die angegebene Ausnahme\-Statusflags erfolgreich festgelegt sind, wird 0 zurückgegeben. Andernfalls wird einen Wert ungleich NULL zurückgegeben.  
  
## Hinweise  
 Die `fesetexceptflag` Funktion legt den Zustand des angegebenen Gleitkommaausnahme Status\-Flags `excepts` mit den entsprechenden Werten der `fexcept_t` Objekt verweist `pstatus`.  Es löst keine Ausnahmen aus. Die `pstatus` Zeiger muss einem gültigen zeigen `fexcept_t` Objekt oder nachfolgendes Verhalten ist nicht definiert. Die `fesetexceptflag` \-Funktion unterstützt diese Ausnahme Makrowerte in `excepts`, die in \< fenv.h \> definiert:  
  
|Ausnahme\-Makro|Beschreibung|  
|---------------------|------------------|  
|FE\_DIVBYZERO|Eine Singularität oder pol Fehler in einer zuvor Gleitkommaoperation; ein Unendlichkeitswert erstellt wurde.|  
|FE\_INEXACT|Die Funktion wurde erzwungen, das gespeicherte Ergebnis einer zuvor Gleitkommaoperation gerundet.|  
|FE\_INVALID|Domänenfehler in einer zuvor Gleitkommaoperation.|  
|FE\_OVERFLOW|Ein Fehler aufgetreten. eine frühere Gleitkommaoperation Ergebnis war zu groß dargestellt werden soll.|  
|FE\_UNDERFLOW|Eine frühere Gleitkommaoperation Ergebnis war zu klein für die bei voller Genauigkeit dargestellt werden; ein Denormal\-Wert wurde erstellt.|  
|FE\_ALLEXCEPT|Der bitweise OR aller unterstützt Gleitkommaausnahmen.|  
  
 Die `excepts` Argument NULL ist, werden möglicherweise einer der unterstützten Gleitkommaausnahme Makros oder das bitweise oder der zwei oder mehr der Makros. Jeder andere Argumentwert wird nicht definiert.  
  
 Um diese Funktion verwenden zu können, müssen Sie wieder deaktivieren Gleitkomma Optimierungen, die Zugriff mithilfe von verhindern könnten die `#pragma fenv_access(on)` Richtlinie vor dem Aufruf. Weitere Informationen finden Sie unter [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`fesetexceptflag`|\<fenv.h\>|\<cfenv\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetexceptflag](../../c-runtime-library/reference/fegetexceptflag2.md)