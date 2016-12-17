---
title: "_onexit, _onexit_m"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_onexit"
  - "_onexit_m"
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
apitype: "DLLExport"
f1_keywords: 
  - "_onexit"
  - "onexit_m"
  - "onexit"
  - "_onexit_m"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "onexit-Funktion"
  - "Registrierung, Registrieren von Beendigungsroutinen"
  - "_onexit_m-Funktion"
  - "onexit_m-Funktion"
  - "_onexit-Funktion"
  - "Registrieren von Beendigungsroutinen"
  - "Registrieren zum Aufruf bei Beendigung"
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# _onexit, _onexit_m
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Registriert eine an der Beendigungszeit aufgerufen werden Routine.  
  
## Syntax  
  
```  
_onexit_t _onexit(  
   _onexit_t function  
);  
_onexit_t_m _onexit_m(  
   _onexit_t_m function  
);  
```  
  
#### Parameter  
 `function`  
 Zeiger auf eine an der Beendigung aufgerufen werden Funktion.  
  
## Rückgabewert  
 `_onexit` gibt einen Zeiger auf die Funktion zurück, wenn erfolgreich oder `NULL`, wenn kein Bereich gibt, z des Funktionszeigers zu speichern.  
  
## Hinweise  
 Der `_onexit` die Adresse einer Funktion wird aufgerufen werden Funktion \(`function`\) übergeben, normalerweise, wenn das Programm beendet wird.  Aufeinander folgende Aufrufe `_onexit` erstellen ein Register von Funktionen, die in Reihenfolge LIFO \(Last\-in\-First\-out\) ausgeführt werden.  Die Funktionen, die an `_onexit` übergeben werden, können keine Parameter enthalten.  
  
 Im Fall, wenn `_onexit` aus einer DLL aufgerufen wird, registriert Routinen mit `_onexit` mit einer DLL entladen werden, nachdem `DllMain` mit DLL\_PROCESS\_DETACH aufgerufen wird.  
  
 `_onexit` ist einer Microsoft\-Erweiterung.  Für ANSI\-Portabilität dem [atexit](../../c-runtime-library/reference/atexit.md).  Die `_onexit_m`\-Version der Funktion ist für Mischverwendung.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_onexit`|\<stdlib.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_onexit.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
/* Prototypes */  
int fn1(void), fn2(void), fn3(void), fn4 (void);  
  
int main( void )  
{  
   _onexit( fn1 );  
   _onexit( fn2 );  
   _onexit( fn3 );  
   _onexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
int fn1()  
{  
   printf( "next.\n" );  
   return 0;  
}  
  
int fn2()  
{  
   printf( "executed " );  
   return 0;  
}  
  
int fn3()  
{  
   printf( "is " );  
   return 0;  
}  
  
int fn4()  
{  
   printf( "This " );  
   return 0;  
}  
```  
  
## Ausgabe  
  
```  
This is executed first.  
This is executed next.  
```  
  
## .NET Framework-Entsprechung  
 [System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_\_dllonexit](../../c-runtime-library/dllonexit.md)