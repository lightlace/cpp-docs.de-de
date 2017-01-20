---
title: "_cwait"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_cwait"
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
  - "api-ms-win-crt-process-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_cwait"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cwait-Funktion"
  - "cwait-Funktion"
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
caps.latest.revision: 23
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# _cwait
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wartet, bis ein anderer Prozess beendet wird.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/en-us/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
intptr_t _cwait(     int *termstat,    intptr_t procHandle,    int action  );  
```  
  
#### Parameter  
 `termstat`  
 Zeiger zu einem Puffer, in dem der Ergebniscode des angegebenen Prozesses gespeichert wird, oder NULL.  
  
 `procHandle`  
 Das Handle für den Prozess, auf den gewartet werden soll \(d. h., der Prozess, der beendet werden muss, bevor `_cwait` zurückgegeben werden kann\).  
  
 `action`  
 NULL: Wird von Anwendungen des Windows\-Betriebssystems ignoriert. Für andere Anwendungen: Für `procHandle` auszuführenden Aktionscode.  
  
## Rückgabewert  
 Wenn der angegebene Vorgang erfolgreich abgeschlossen wurde, wird das Handle des angegebenen Prozesses zurückgegeben und `termstat` auf den Ergebniscode festgelegt, der vom angegebenen Prozess zurückgegeben wird.  Andernfalls wird –1 zurückgegeben und `errno` wie folgt festgelegt.  
  
|Wert|Beschreibung|  
|----------|------------------|  
|`ECHILD`|Es ist kein angegebener Prozess vorhanden, `procHandle` ist ungültig, oder der Aufruf der API [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx) oder der API [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx) ist fehlgeschlagen.|  
|`EINVAL`|`action` ist ungültig.|  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_cwait`\-Funktion wartet auf die Beendigung der Prozess\-ID des angegebenen Prozesses, die von `procHandle` bereitgestellt wird.  Der Wert von `procHandle`, der an `_cwait` übergeben wird, sollte der Wert sein, der vom Aufruf der [\_spawn](../../c-runtime-library/spawn-wspawn-functions.md)\-Funktion zurückgegeben wird, die den angegebenen Prozess erstellt hat.  Wenn die Prozess\-ID vor dem Aufruf von `_cwait` beendet wird, wird `_cwait` sofort zurückgegeben.  `_cwait` kann von jedem Prozess verwendet werden, um auf jeden anderen bekannten Prozess zu warten, für den ein gültiges Handle \(`procHandle`\) vorhanden ist.  
  
 `termstat` weist auf einen Puffer hin, in dem der Rückgabecode des angegebenen Prozesses gespeichert wird.  Der Wert von `termstat` gibt an, ob der angegebene Prozess regulär durch Aufruf der Windows\-API [ExitProcess](http://msdn.microsoft.com/library/windows/desktop/ms682658.aspx) beendet wurde.  `ExitProcess` wird intern aufgerufen, wenn der angegebene Vorgang `exit` oder `_exit` aufruft, von `main` zurückkehrt oder das Ende von `main` erreicht.  Weitere Informationen über den Wert, der durch `termstat` zurückübergeben wird, finden Sie unter [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx).  Wenn `_cwait` durch Verwenden eines NULL\-Werts für `termstat` aufgerufen wird, wird der Rückgabecode des angegebenen Prozesses nicht gespeichert.  
  
 Der `action`\-Parameter wird vom Windows\-Betriebssystem ignoriert, da Beziehungen zwischen übergeordneten und untergeordneten Elementen in diesen Umgebungen nicht implementiert werden.  
  
 Sofern `procHandle` nicht \-1 oder \-2 ist \(Handles für den aktuellen Prozess oder Thread\), wird das Handle geschlossen.  Daher sollte in dieser Situation das zurückgegebene Handle nicht verwendet werden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_cwait`|\<process.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_cwait.c  
// compile with: /c  
// This program launches several processes and waits  
// for a specified process to finish.  
//  
#define _CRT_RAND_S  
  
#include <windows.h>  
#include <process.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <time.h>  
  
// Macro to get a random integer within a specified range  
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))  
  
struct PROCESS  
{  
   int     nPid;  
   char    name[40];  
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };  
  
int main( int argc, char *argv[] )  
{  
   int termstat, c;  
   unsigned int number;  
  
   srand( (unsigned)time( NULL ) );    // Seed randomizer  
  
   // If no arguments, this is the calling process  
   if( argc == 1 )  
   {  
      // Spawn processes in numeric order  
      for( c = 0; c < 4; c++ ){  
         _flushall();  
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],   
                             process[c].name, NULL );  
      }  
  
      // Wait for randomly specified process, and respond when done   
      c = getrandom( 0, 3 );  
      printf( "Come here, %s.\n", process[c].name );  
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );  
      printf( "Thank you, %s.\n", process[c].name );  
  
   }  
   // If there are arguments, this must be a spawned process   
   else  
   {  
      // Delay for a period that's determined by process number  
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );  
      printf( "Hi, Dad. It's %s.\n", argv[1] );  
   }  
}  
```  
  
  **Hallo, Vati.  Hier ist Ann.  Komm her, Ann.  Danke, Ann.  Hallo, Vati.  Hier ist Beth.  Hallo, Vati.  Hier ist Carl.  Hallo, Vati.  Hier ist Dave.**    
## .NET Framework-Entsprechung  
 [System::Diagnostics::Process::WaitForExit](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [\_spawn\- und \_wspawn\-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)