---
title: "feclearexcept1 | Microsoft Docs"
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
  - "feclearexcept"
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
  - "feclearexcept"
  - "fenv/feclearexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Feclearexcept-Funktion"
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# feclearexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versucht, die durch das Argument angegebenen Gleitkommaausnahme Flags zu deaktivieren.  
  
## Syntax  
  
```  
int feclearexcept(  
   int excepts  
);  
```  
  
#### Parameter  
 `excepts`  
 Die Ausnahme Statusflags zu deaktivieren.  
  
## Rückgabewert  
 Gibt 0, wenn `excepts` null ist, oder wenn alle angegebenen Ausnahmen wurden erfolgreich gelöscht wurden. Andernfalls wird einen Wert ungleich NULL zurückgegeben.  
  
## Hinweise  
 Die `feclearexcept` Funktion versucht wurde, deaktivieren Sie die Gleitkommaoperationen zeigen Ausnahme Status\-Flags, die durch angegebene `excepts`. Die Funktion unterstützt diese Ausnahmemakros in fenv.h definiert:  
  
|Ausnahme\-Makro|Beschreibung|  
|---------------------|------------------|  
|FE\_DIVBYZERO|Eine Singularität oder pol Fehler in einer zuvor Gleitkommaoperation; ein Unendlichkeitswert erstellt wurde.|  
|FE\_INEXACT|Die Funktion wurde erzwungen, das gespeicherte Ergebnis einer zuvor Gleitkommaoperation gerundet.|  
|FE\_INVALID|Domänenfehler in einer zuvor Gleitkommaoperation.|  
|FE\_OVERFLOW|Ein Fehler aufgetreten. eine frühere Gleitkommaoperation Ergebnis war zu groß dargestellt werden soll.|  
|FE\_UNDERFLOW|Eine frühere Gleitkommaoperation Ergebnis war zu klein für die bei voller Genauigkeit dargestellt werden; ein Denormal\-Wert wurde erstellt.|  
|FE\_ALLEXCEPT|Der bitweise OR aller unterstützt Gleitkommaausnahmen.|  
  
 Die `excepts` Argument 0 \(null\) oder die bitweise OR von mindestens einem der unterstützten Ausnahmemakros sein. Das Ergebnis jeder andere Argumentwert ist nicht definiert.  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`feclearexcept`|\<fenv.h\>|\<cfenv\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)