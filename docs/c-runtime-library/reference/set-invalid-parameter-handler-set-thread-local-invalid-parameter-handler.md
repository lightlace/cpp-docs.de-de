---
title: "_set_invalid_parameter_handler _set_thread_local_invalid_parameter_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_invalid_parameter_handler"
  - "_set_thread_local_invalid_parameter_handler"
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
  - "set_invalid_parameter_handler"
  - "_set_invalid_parameter_handler"
  - "_set_thread_local_invalid_parameter_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ungültiger Parametertyphandler"
  - "set_invalid_parameter_handler-Funktion"
  - "_set_invalid_parameter_handler-Funktion"
  - "_set_thread_local_invalid_parameter_handler-Funktion"
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _set_invalid_parameter_handler _set_thread_local_invalid_parameter_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt eine Funktion aufgerufen werden, wenn die CRT ein ungültiges Argument entdeckt.  
  
## Syntax  
  
```  
_invalid_parameter_handler _set_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
_invalid_parameter_handler _set_thread_local_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
```  
  
#### Parameter  
 \[in\] `pNew`  
 Der Funktionszeiger, der neue Handler für ungültige Parameter.  
  
## Rückgabewert  
 Ein Zeiger auf den Handler für ungültige Parameter vor dem Aufruf.  
  
## Hinweise  
 Viele Funktionen der C\-Runtime überprüft die Gültigkeit der an sie übergebenen Argumente. Wenn ein ungültiges Argument übergeben wird, die Funktion lassen sich die `errno` Fehlernummer oder einen Fehlercode zurück. In solchen Fällen wird der Handler für ungültige Parameter auch bezeichnet. Der C\-Laufzeitbibliothek stellt einen Standardhandler für das globale Ungültiger Parameter, der das Programm beendet und die Laufzeit eine Fehlermeldung angezeigt. Sie können die `_set_invalid_parameter_handler` um eine eigene Funktion als Handler für globale ungültige Parameter festzulegen. Der C\-Laufzeitbibliothek unterstützt auch einen Handler für ungültige Parameter threadlokalen. Wenn ein Handler lokalen Thread\-Parameter in einem Thread festgelegt ist, mithilfe von `_set_thread_local_invalid_parameter_handler`, die Funktionen der C\-Laufzeit aus dem Thread aufgerufen,\-Handler anstelle der globalen Handler verwendet. Nur eine Funktion kann gleichzeitig als Handler globale Ungültiges Argument angegeben werden. Nur eine Funktion kann als ungültiges Argument threadlokalen Handler pro Thread angegeben werden, jedoch verschiedene Threads können unterschiedliche Thread\-Local\-Handler verfügen. Dadurch können Sie den Handler in einem Teil des Codes ohne Auswirkung auf das Verhalten anderer Threads zu ändern.  
  
 Wenn die Common Language Runtime die ungültige Parameter\-Funktion aufruft, bedeutet dies normalerweise, dass ein nicht behebbarer Fehler aufgetreten ist. Die Handlerfunktion für ungültige Parameter, die Sie bereitstellen sollten Daten kann und brechen dann speichern. Es sollte der main\-Funktion keine Steuerung zurück, wenn Sie sicher sind, dass der Fehler behoben werden kann.  
  
 Die Handlerfunktion für ungültige Parameter muss den folgenden Prototyp aufweisen:  
  
```c  
void _invalid_parameter(  
   const wchar_t * expression,  
   const wchar_t * function,   
   const wchar_t * file,   
   unsigned int line,  
   uintptr_t pReserved  
);  
```  
  
 Die `expression` Argument ist eine Breite Zeichenfolge\-Darstellung des Expression\-Arguments, das den Fehler ausgelöst hat. Die `function` Argument ist der Name der CRT\-Funktion, die die ungültige Argument empfangen. Die `file` Argument ist der Name der CRT\-Quelldatei, die die Funktion enthält. Die `line` Argument ist die Nummer der Zeile in der Datei. Das letzte Argument ist reserviert. Die Parameter haben den Wert `NULL` wenn eine Debugversion der CRT\-Bibliothek verwendet wird.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_set_invalid_parameter_handler`, `_set_thread_local_invalid_parameter_handler`|C: \< stdlib.h \><br /><br /> C\+\+: \< Cstdlib \> oder \< stdlib.h \>|  
  
 Die `_set_invalid_parameter_handler` und `_set_thread_local_invalid_parameter_handler` Funktionen sind Microsoft\-spezifisch. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Im folgenden Beispiel wird ein Fehler\-Handler für ungültige Parameter verwendet, um die Funktion zu drucken, die den ungültigen Parameter und die Datei\- und Linie CRT\-Quellen erhalten haben. Ungültiger Parameter Fehler auslösen, wenn der CRT\-Debugbibliothek verwendet wird, auch eine Assertion, die in diesem Beispiel verwenden deaktiviert ist [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md).  
  
```c  
// crt_set_invalid_parameter_handler.c  
// compile with: /Zi /MTd  
#include <stdio.h>  
#include <stdlib.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
  
void myInvalidParameterHandler(const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter detected in function %s."  
            L" File: %s Line: %d\n", function, file, line);  
   wprintf(L"Expression: %s\n", expression);  
   abort();  
}  
  
int main( )  
{  
   char* formatString;  
  
   _invalid_parameter_handler oldHandler, newHandler;  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   // Call printf_s with invalid parameters.  
  
   formatString = NULL;  
   printf(formatString);  
}  
```  
  
```Output  
Ungültiger Parameter in Funktion Common_vfprintf erkannt. Datei: minkernel\crts\ucrt\src\appcrt\stdio\output.cpp Zeile: 32 Ausdruck: Format! = "nullptr"  
```  
  
## Siehe auch  
 [\_get\_invalid\_parameter\_handler \_get\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)   
 [CRT\-Funktionsversionen mit erweiterter Sicherheit](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)   
 [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)