---
title: "fetestexcept"
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
  - "fetestexcept"
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
  - "fetestexcept"
  - "fenv/fetestexcept"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "Fetestexept-Funktion"
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# fetestexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, welcher der angegebenen Gleitkommaausnahme Status\-Flags momentan festgelegt sind.  
  
## Syntax  
  
```  
int fetestexcept(  
   int excepts  
);  
  
```  
  
#### Parameter  
 `excepts`  
 Eine bitweise OR Gleitkomma\-Status\-Flags zu testen.  
  
## Rückgabewert  
 Legen bei Erfolg gibt eine Bitmaske, die mit einer bitweisen OR der Gleitkommaausnahme Makros, die derzeit den Ausnahme\-Status\-Flags entsprechen. Gibt 0, wenn keine Ausnahmen werden festgelegt.  
  
## Hinweise  
 Verwenden Sie die Fetestexcept\-Funktion, um zu bestimmen, welche Ausnahmen ausgelöst wurden, durch einen Gleitkommawert Vorgang zeigen. Verwenden der `excepts` Parameter, um die Ausnahme\-Status\-Flags zu testen. Die `fetestexcept` \-Funktion verwendet diese in \< fenv.h \> in Ausnahmemakros `excepts` und der Rückgabewert:  
  
|Ausnahme\-Makro|Beschreibung|  
|---------------------|------------------|  
|FE\_DIVBYZERO|Eine Singularität oder pol Fehler in einer zuvor Gleitkommaoperation; ein Unendlichkeitswert erstellt wurde.|  
|FE\_INEXACT|Die Funktion wurde erzwungen, das gespeicherte Ergebnis einer zuvor Gleitkommaoperation gerundet.|  
|FE\_INVALID|Domänenfehler in einer zuvor Gleitkommaoperation.|  
|FE\_OVERFLOW|Ein Fehler aufgetreten. eine frühere Gleitkommaoperation Ergebnis war zu groß dargestellt werden soll.|  
|FE\_UNDERFLOW|Eine frühere Gleitkommaoperation Ergebnis war zu klein für die bei voller Genauigkeit dargestellt werden; ein Denormal\-Wert wurde erstellt.|  
|FE\_ALLEXCEPT|Der bitweise OR aller unterstützt Gleitkommaausnahmen.|  
  
 Das angegebene `excepts` Argument kann 0 sein, einer der unterstützten Gleitkommaausnahme Makros oder das bitweise oder der zwei oder mehr der Makros. Die Auswirkung eines anderen `excepts` Argumentwert ist nicht definiert.  
  
 Um diese Funktion verwenden zu können, müssen Sie wieder deaktivieren Gleitkomma Optimierungen, die Zugriff mithilfe von verhindern könnten die `#pragma fenv_access(on)` Richtlinie vor dem Aufruf. Weitere Informationen finden Sie unter [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`fetestexcept`|\<fenv.h\>|\<cfenv\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feraiseexcept](../../c-runtime-library/reference/feraiseexcept.md)