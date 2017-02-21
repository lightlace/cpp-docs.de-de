---
title: "quick_exit1 | Microsoft Docs"
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
  - "quick_exit"
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
  - "quick_exit"
  - "process/quick_exit"
  - "stdlib/quick_exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "quick_exit-Funktion"
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# quick_exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bewirkt eine normale Programmbeendigung.  
  
## Syntax  
  
```  
__declspec(noreturn) void quick_exit(  
    int status  
);  
```  
  
#### Parameter  
 Status  
 Der an die Hostumgebung zurückzugebende Statuscode.  
  
## Rückgabewert  
 Die `quick_exit`\-Funktion kann nichts an den Aufrufer zurückgeben.  
  
## Hinweise  
 Die `quick_exit`\-Funktion bewirkt eine normale Programmbeendigung. Sie ruft keine von `atexit` oder `_onexit` registrierten Funktionen oder durch die `signal`\-Funktion registrierten Signalhandler auf. Das Verhalten ist undefiniert, wenn `quick_exit` mehrfach aufgerufen wird oder wenn die Funktion `exit` ebenfalls aufgerufen wird.  
  
 Die Funktion `quick_exit` ruft die von `at_quick_exit` registrierten Funktionen in LIFO\-Reihenfolge \(Last\-In, First\-Out\) auf, abgesehen von den beim Registrieren der Funktion bereits aufgerufenen Funktionen.  Da Verhalten ist undefiniert, wenn ein [longjmp](../../c-runtime-library/reference/longjmp.md)\-Aufruf während des Aufrufs einer registrierten Funktion erfolgt, die den Aufruf der Funktion beenden würde.  
  
 Nachdem die registrierten Funktionen aufgerufen wurden, ruft `quick_exit``_Exit` auf und verwendet dazu den `status`\-Wert, um die Steuerung an die Hostumgebung zurückzugeben.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`quick_exit`|\<process.h\> oder \<stdlib.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_exec\- und \_wexec\-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_spawn\- und \_wspawn\-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)