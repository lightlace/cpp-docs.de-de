---
title: "fegetexceptflag"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "fegetexceptflag"
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
  - "fegetexceptflag"
  - "fenv/fegetexceptflag"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "Fegetexceptflag-Funktion"
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# fegetexceptflag
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Speichert den aktuellen Zustand der angegebenen Gleitkommaausnahme Flags.  
  
## Syntax  
  
```  
int fegetexceptflag(   
   fexcept_t* pstatus,   
   int excepts   
);  
  
```  
  
#### Parameter  
 `pstatus`  
 Ein Zeiger auf ein `fexcept_t` Objekt, das die aktuellen Werte der angegebenen Ausnahme\-Flags enthalten `excepts`.  
  
 `excepts`  
 Die Gleitkomma\-Ausnahme\-Flags zum Speichern in `pstatus`.  
  
## Rückgabewert  
 Bei Erfolg zurückgegeben 0. Andernfalls wird einen Wert ungleich NULL zurückgegeben.  
  
## Hinweise  
 Die `fegetexceptflag` Funktion speichert den aktuellen Zustand der Gleitkommaausnahme Status\-Flags, die durch angegebene `excepts` in der `fexcept_t` Objekt verweist `pstatus`.`pstatus` muss einen Verweis auf eine gültige `fexcept_t` Objekt oder nachfolgendes Verhalten ist nicht definiert. Die `fegetexceptflag` \-Funktion unterstützt diese Ausnahmemakros in \< fenv.h \> definiert:  
  
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
|`fegetexceptflag`|\<fenv.h\>|\<cfenv\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)