---
title: "atexit"
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
  - "atexit"
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
  - "atexit"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "atexit-Funktion"
  - "Verarbeiten, bei Beenden"
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# atexit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verarbeitet die angegebene Funktion angezeigt der Beendigung.  
  
## Syntax  
  
```  
int atexit(  
   void (__cdecl *func )( void )  
);  
```  
  
#### Parameter  
 `func`  
 Wird werden Funktion.  
  
## Rückgabewert  
 `atexit` gibt 0 zurück, wenn erfolgreich oder einen Wert ungleich 0 \(null\), wenn ein Fehler auftritt.  
  
## Hinweise  
 Der `atexit` die Adresse einer Funktion wird aufgerufen werden Funktion \(`func`\) übergeben, normalerweise, wenn das Programm beendet wird.  Aufeinander folgende Aufrufe `atexit` erstellen ein Register von Funktionen, die in Reihenfolge Last in, First out \(LIFO\) ausgeführt werden.  Die Funktionen, die an `atexit` übergeben werden, können keine Parameter enthalten.  `atexit` und `_onexit` verwenden, um den Heap das Register von Funktionen aufzunehmen.  Somit wird die Anzahl von Funktionen, die so registriert werden, können nur durch Heapspeicher beschränkt.  
  
 Der Code in der Funktion `atexit` sollte keine Abhängigkeit einer DLL enthalten, die bereits entladen worden sein könnte, wenn die `atexit`\-Funktion aufgerufen wird.  
  
 Um eine ANSI\-kompatible Anwendung zu generieren, verwenden Sie die `atexit` ANSI\-Standard Funktion \(anstatt die `_onexit` ähnliche Funktion\).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`atexit`|\<stdlib.h\>|  
  
## Beispiel  
 Dieses Programm drückt vier Funktionen auf dem Stapel von den ausgeführten Funktionen, wenn `atexit` aufgerufen wird.  Wenn das Programm wird, diese Programmen auf einem Letzten ausgeführt werden, First Out Basis.  
  
```  
// crt_atexit.c  
#include <stdlib.h>  
#include <stdio.h>  
  
void fn1( void ), fn2( void ), fn3( void ), fn4( void );  
  
int main( void )  
{  
   atexit( fn1 );  
   atexit( fn2 );  
   atexit( fn3 );  
   atexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
void fn1()  
{  
   printf( "next.\n" );  
}  
  
void fn2()  
{  
   printf( "executed " );  
}  
  
void fn3()  
{  
   printf( "is " );  
}  
  
void fn4()  
{  
   printf( "This " );  
}  
```  
  
  **Dies wird zuerst ausgeführt.**  
**Dies wird als Nächstes ausgeführt.**   
## .NET Framework-Entsprechung  
 [System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)