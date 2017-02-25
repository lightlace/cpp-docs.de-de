---
title: "feupdateenv | Microsoft Docs"
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
  - "feupdateenv"
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
  - "feupdateenv"
  - "fenv/feupdateenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Feupdateenv-Funktion"
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# feupdateenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Speichert die aktuell ausgelösten Ausnahmen, stellt die angegebene Gleitkommazahl Umgebung Zustand wieder her und löst dann die gespeicherten Gleitkommaausnahmen.  
  
## Syntax  
  
```  
int feupdateenv(  
   const fenv_t* penv  
);  
```  
  
#### Parameter  
 `penv`  
 Zeiger auf ein `fenv_t` Objekt, das eine Gleitkommazahl Umgebung festgelegt durch einen Aufruf von enthält [fegetenv](../Topic/fegetenv2.md) oder [feholdexcept](../Topic/feholdexcept1.md). Sie können auch Standard Gleitkomma Autostart angeben, indem Sie das FE\_DFL\_ENV\-Makro.  
  
## Rückgabewert  
 Gibt 0 zurück, wenn alle Aktionen erfolgreich abgeschlossen wurde. Andernfalls wird einen Wert ungleich NULL zurückgegeben.  
  
## Hinweise  
 Die `feupdateenv` \-Funktion führt mehrere Aktionen. Zunächst werden die aktuellen ausgelöste Gleitkommaausnahme Status\-Flags in automatischen Speicher gespeichert. Dann wird die aktuelle Gleitkomma\-Umgebung aus den in gespeicherten Wert der `fenv_t` Objekt verweist `penv`. Wenn `penv` nicht FE\_DFL\_ENV oder verweist nicht auf eine gültige `fenv_t` \-Objekt nachfolgendes Verhalten ist nicht definiert. Schließlich `feupdateenv` löst die lokal gespeicherten Gleitkommaausnahmen.  
  
 Um diese Funktion verwenden zu können, müssen Sie wieder deaktivieren Gleitkomma Optimierungen, die Zugriff mithilfe von verhindern könnten die `#pragma fenv_access(on)` Richtlinie vor dem Aufruf. Weitere Informationen finden Sie unter [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`feupdateenv`|\<fenv.h\>|\<cfenv\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)