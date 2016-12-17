---
title: "set_unexpected (CRT)"
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
  - "set_unexpected"
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
  - "set_unexpected"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Ausnahmebehandlung, Terminierung"
  - "set_unexpected-Funktion"
  - "Unerwarteter Funktionstyp"
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# set_unexpected (CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Installiert eigene von `unexpected` aufgerufen werden, Beendigungsfunktion.  
  
## Syntax  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### Parameter  
 `unexpFunction`  
 Zeiger auf eine Funktion, die Sie schreiben, um die Funktion `unexpected` zu ersetzen.  
  
## Rückgabewert  
 Gibt einen Zeiger zur vorherigen Beendigungsfunktion zurück, die von `_set_unexpected` registriert wird, dass die vorherige Funktion später wiederhergestellt werden kann.  Wenn keine vorherige Funktion festgelegt wurde, wird der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen; Dieser Wert kann NULL.  
  
## Hinweise  
 Die `set_unexpected`\-Funktion installiert `unexpFunction` als Funktion, die durch `unexpected` aufgerufen wird.  `unexpected` wird nicht in der aktuellen C\+\+\-Ausnahmebehandlungsimplementierung verwendet.  Der Typ `unexpected_function` wird in EH.H als Zeiger zu einer unerwarteten benutzerdefinierten Funktion, `unexpFunction` definiert, die `void` zurückgibt.  Die benutzerdefinierte `unexpFunction`\-Funktion sollte nicht an dessen Aufrufer zurückzukehren.  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 Standardmäßig `unexpected` Aufrufe `terminate`.  Sie können dieses Standardverhalten ändern, indem Sie die eigene Beendigungsfunktion schreiben und `set_unexpected` mit dem Namen der Funktion als Argument aufrufen.  `unexpected` ruft die letzte Funktion angegeben `set_unexpected` als Argument auf.  
  
 Anders als benutzerdefinierte Beendigungsfunktion, die bei einem Aufruf von `set_terminate` installiert ist, kann eine Ausnahme `unexpFunction` ausgelöst werden.  
  
 In einer Multithreadumgebung werden unerwartete Funktionen separat für jeden Thread beibehalten.  Anforderungen der neue Threads, eine eigenen unerwartete Funktion zu installieren.  Daher ist jeder Thread verantwortlich für seine eigene unerwartete Behandlung.  
  
 In der aktuellen Implementierung der C\+\+\-Ausnahmebehandlung Ausnahmebehandlung, ruft `unexpected` standardmäßig `terminate` auf und wird nicht von der Ausnahmebehandlungslaufzeitbibliothek aufgerufen.  Es gibt keinen besonderen Vorteil dem Aufrufen von `unexpected` und nicht `terminate`.  
  
 Es gibt einen einzelnen `set_unexpected`\-Handler für alle dynamisch verknüpfte DLLs oder EXE\-Dateien; wenn Sie `set_unexpected` aufrufen, wird der Handler ersetzt durch andere möglicherweise, das oder ersetzen Sie einen Handler, der von einer anderen DLL oder EXE\-Datei festgelegt wird.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`set_unexpected`|\<eh.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_get\_unexpected](../../c-runtime-library/reference/get-unexpected.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)