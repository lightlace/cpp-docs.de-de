---
title: "_get_invalid_parameter_handler _get_thread_local_invalid_parameter_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_invalid_parameter_handler"
  - "_get_thread_local_invalid_parameter_handler"
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
  - "_get_invalid_parameter_handler"
  - "stdlib/_get_invalid_parameter_handler"
  - "_get_thread_local_invalid_parameter_handler"
  - "stdlib/_get_thread_local_invalid_parameter_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_thread_local_invalid_parameter_handler-Funktion"
  - "_get_invalid_parameter_handler-Funktion"
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# _get_invalid_parameter_handler _get_thread_local_invalid_parameter_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Funktion, die aufgerufen wird, wenn die CRT ein ungültiges Argument entdeckt.  
  
## Syntax  
  
```  
_invalid_parameter_handler _get_invalid_parameter_handler(void);  
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);  
```  
  
## Rückgabewert  
 Ein Zeiger auf die derzeit festgelegten Handlerfunktion Ungültiger Parameter oder ein null\-Zeiger, wenn keine festgelegt wurde.  
  
## Hinweise  
 Die `_get_invalid_parameter_handler` Funktion ruft die derzeit festgelegten Handler für globale ungültige Parameter. Gibt einen null\-Zeiger, wenn kein Handler globale Ungültiger Parameter festgelegt wurde. Auf ähnliche Weise die `_get_thread_local_invalid_parameter_handler` Ruft aktuelle Handler für ungültige Thread\-Local\-Parameter für den Thread, der für aufgerufen wird, oder ein null\-Zeiger, wenn kein Handler festgelegt wurde. Informationen zum Festlegen von globalen und lokalen Thread\-Ungültiger Parameter Handler finden Sie unter [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).  
  
 Der zurückgegebene ungültige Parameter Handler Funktionszeiger hat den folgenden Typ:  
  
```c  
typedef void (__cdecl* _invalid_parameter_handler)(  
    wchar_t const*,  
    wchar_t const*,  
    wchar_t const*,   
    unsigned int,  
    uintptr_t  
    );  
```  
  
 Details zu den Handler für ungültige Parameter, finden Sie unter den Prototyp in [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_invalid_parameter_handler`, `_get_thread_local_invalid_parameter_handler`|C: \< stdlib.h \><br /><br /> C\+\+: \< Cstdlib \> oder \< stdlib.h \>|  
  
 Die `_get_invalid_parameter_handler` und `_get_thread_local_invalid_parameter_handler` Funktionen sind Microsoft\-spezifisch. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)   
 [CRT\-Funktionsversionen mit erweiterter Sicherheit](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)