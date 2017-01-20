---
title: "_cexit, _c_exit"
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
  - "_c_exit"
  - "_cexit"
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
  - "_cexit"
  - "c_exit"
  - "_c_exit"
  - "cexit"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_c_exit-Funktion"
  - "_cexit-Funktion"
  - "c_exit-Funktion"
  - "cexit-Funktion"
  - "Säuberungsvorgänge während des Prozesses"
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# _cexit, _c_exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt Bereinigungsvorgänge aus und wird zurückgegeben, ohne den Prozess zu beenden.  
  
## Syntax  
  
```  
void _cexit( void );  
void _c_exit( void );  
```  
  
## Hinweise  
 Die `_cexit`\-Funktionsaufrufe, in Reihenfolge Last in, First out \(LIFO\), die registrierten Funktionen von `atexit` und `_onexit`.  Anschließend leert `_cexit` alle E\/A\-Puffer und schließt alle geöffneten Streams, bevor zurückkehrt.  `_c_exit` entspricht `_exit` gibt zum aufrufenden Prozesses, ohne `atexit` oder `_onexit` zu verarbeiten oder Streampuffer zu entfernen.  Das Verhalten von `exit`,`_exit`, `_cexit` und `_c_exit` wird in der folgenden Tabelle gezeigt.  
  
|Funktion|Verhalten|  
|--------------|---------------|  
|`exit`|Führt vollständige C\-Bibliotheksbeendigungsprozeduren aus, beendet Prozess und endet mit angegebenem Statuscode.|  
|`_exit`|Führt schnelle C\-Bibliotheksbeendigungsprozeduren aus, beendet Prozess und endet mit angegebenem Statuscode.|  
|`_cexit`|Führt vollständige C\-Bibliotheksbeendigungsprozeduren aus und kehren zum Aufrufer zurück, endet jedoch nicht Prozess.|  
|`_c_exit`|Führt schnelle C\-Bibliotheksbeendigungsprozeduren aus und kehren zum Aufrufer zurück, endet jedoch nicht Prozess.|  
  
 Wenn Sie aufrufen, werden die `_cexit``_c_exit` oder Funktionen, die Destruktoren für keine temporären oder automatische Objekte, die zum Zeitpunkt des Aufrufs vorhanden, nicht aufgerufen.  Ein automatisches Objekt ist ein Objekt, das in einer Funktion definiert ist, in der das Objekt nicht deklariert, um statisch sein.  Ein temporäres Objekt ist ein Objekt, das vom Compiler erstellt wird.  Um ein automatisches Objekt bevor Sie `_cexit` oder `_c_exit` zu zerstören aufrufen, erhalten Sie den Destruktor explizit für das Objekt auf, wie folgt:  
  
```  
myObject.myClass::~myClass( );  
```  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_cexit`|\<process.h\>|  
|`_c_exit`|\<process.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 [System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_exec\- und \_wexec\-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_spawn\- und \_wspawn\-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)