---
title: "set_terminate (CRT)"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "set_terminate"
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
  - "set_terminate"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Ausnahmebehandlung, Terminierung"
  - "set_terminate-Funktion"
  - "terminate-Funktion"
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# set_terminate (CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Installiert eigene von `terminate` aufgerufen werden, Enderoutine.  
  
## Syntax  
  
```  
terminate_function set_terminate(  
   terminate_function termFunction  
);  
```  
  
#### Parameter  
 `termFunction`  
 Zeiger auf eine beendensfunktion, die Sie schreiben.  
  
## Rückgabewert  
 Gibt einen Zeiger an die vorherige Funktion zurück, die von `set_terminate` registriert wird, dass die vorherige Funktion später wiederhergestellt werden kann.  Wenn keine vorherige Funktion festgelegt wurde, wird der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen; Dieser Wert kann NULL.  
  
## Hinweise  
 Die `set_terminate`\-Funktion installiert `termFunction` als Funktion, die durch `terminate` aufgerufen wird.  `set_terminate` wird mit der behandelnden C\+\+\-Ausnahme und auf jedem Punkt im Programm aufgerufen werden, bevor die Ausnahme ausgelöst wird.  Aufrufe `terminate` standardmäßig `abort`.  Sie können diese Standardeinstellung ändern, indem Sie die eigene Beendigungsfunktion schreiben und `set_terminate` mit dem Namen der Funktion als Argument aufrufen.  `terminate` ruft die letzte Funktion angegeben `set_terminate` als Argument auf.  Nachdem es dabei gewünschten Bereinigungsaufgaben ausgeführt wurde, sollte `termFunction` das Programm beenden.  Wenn nicht beendet \(wenn es an dessen Aufrufer\), wird `abort` aufgerufen.  
  
 In einer Multithreadumgebung beenden Sie Funktionen werden separat verwaltet für jeden Thread.  Anforderungen jedes beenden neue Threads, eigene Funktion zu installieren.  Daher ist jeder Thread verantwortlich für die eigene Beendigungsbehandlung.  
  
 Der Typ `terminate_function` wird in EH.H als Zeiger auf einer benutzerdefinierten Beendigungsfunktion, `termFunction` definiert, die `void` zurückgibt.  Ihre benutzerdefinierte Funktion `termFunction` kann keine Argumente akzeptieren und sollte nicht an dessen Aufrufer zurückzukehren.  Wenn ja, wird `abort` aufgerufen.  Eine Ausnahme wird nicht aus `termFunction` ausgelöst werden.  
  
```  
typedef void ( *terminate_function )( );  
```  
  
> [!NOTE]
>  Die `set_terminate`\-Funktion funktioniert nur außerhalb des Debuggers.  
  
 Es gibt einen einzelnen `set_terminate`\-Handler für alle dynamisch verknüpfte DLLs oder EXE\-Dateien; wenn Sie `set_terminate` aufrufen, wird der Handler durch andere ersetzt werden, oder ersetzen Sie möglicherweise einen Handler, der von einer anderen DLL oder EXE\-Datei festgelegt wird.  
  
 Diese Funktion wird unter **\/clr:pure** nicht unterstützt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`set_terminate`|\<eh.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Im Beispiel für [Beenden Sie](../../c-runtime-library/reference/terminate-crt.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_get\_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)