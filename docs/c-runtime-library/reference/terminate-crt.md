---
title: "terminate (CRT)"
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
  - "terminate"
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
  - "terminate"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Ausnahmebehandlung, Terminierung"
  - "terminate-Funktion"
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# terminate (CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aufrufe `abort` oder Funktion, die Sie mit `set_terminate` angeben.  
  
## Syntax  
  
```  
void terminate( void );  
```  
  
## Hinweise  
 Die `terminate`\-Funktion wird der mit behandelnden C\+\+\-Ausnahme verwendet und ist in den folgenden Fällen aufgerufen:  
  
-   Ein entsprechender catch\-Handler kann nicht für eine ausgelöste C\+\+\-Ausnahme gefunden werden.  
  
-   Eine Ausnahme wird durch einer Destruktorfunktion während der Stapelentladung ausgelöst.  
  
-   Der Stapel ist beschädigt, nachdem der eine Ausnahme ausgelöst hat.  
  
 Aufrufe `terminate` standardmäßig `abort`.  Sie können diese Standardeinstellung ändern, indem Sie die eigene Beendigungsfunktion schreiben und `set_terminate` mit dem Namen der Funktion als Argument aufrufen.  `terminate` ruft die letzte Funktion angegeben `set_terminate` als Argument auf.  Weitere Informationen finden Sie unter [Nicht behandelte C\+\+\-Ausnahmen](../../cpp/unhandled-cpp-exceptions.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`terminate`|\<eh.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_terminate.cpp  
// compile with: /EHsc  
#include <eh.h>  
#include <process.h>  
#include <iostream>  
using namespace std;  
  
void term_func();  
  
int main()  
{  
    int i = 10, j = 0, result;  
    set_terminate( term_func );  
    try  
    {  
        if( j == 0 )  
            throw "Divide by zero!";  
        else  
            result = i/j;  
    }  
    catch( int )  
    {  
        cout << "Caught some integer exception.\n";  
    }  
    cout << "This should never print.\n";  
}  
  
void term_func()  
{  
    cout << "term_func() was called by terminate().\n";  
  
    // ... cleanup tasks performed here  
  
    // If this function does not exit, abort is called.  
  
    exit(-1);  
}  
```  
  
  **term\_func\(\) wurde durch terminate\(\)aufgerufen.**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)