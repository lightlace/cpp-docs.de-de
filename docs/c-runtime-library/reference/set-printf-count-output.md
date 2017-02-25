---
title: "_set_printf_count_output | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_printf_count_output"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_printf_count_output"
  - "_set_printf_count_output"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%n-Format"
  - "_set_printf_count_output-Funktion"
  - "set_printf_count_output-Funktion"
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _set_printf_count_output
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aktivieren oder deaktivieren Sie Unterstützung `%n` des Stils in [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\- Familienfunktionen.  
  
## Syntax  
  
```  
int _set_printf_count_output(  
   int enable  
);  
```  
  
#### Parameter  
 `enable`  
 Ein Wert ungleich 0 \(null\), um `%n` Unterstützung, 0 zu ermöglichen, dass `%n` Unterstützung zu deaktivieren.  
  
## Eigenschaftswert\/Rückgabewert  
 Der Zustand von `%n` Unterstützung, bevor dieser Funktion wird: Wert ungleich 0 \(null\), wenn `%n` Unterstützung aktiviert wurde, 0, wenn sie deaktiviert wurde.  
  
## Hinweise  
 Aufgrund der Sicherheitsüberlegungen wird Unterstützung für den `%n` Formatbezeichner standardmäßig in `printf` und allen seinen Varianten deaktiviert.  Wenn `%n` in einer `printf` Formatangabe vorkommt, ist das Standardverhalten, der ungültige Parameterhandler aufzurufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Das Aufrufen von `_set_printf_count_output` mit einem Argument ungleich 0 \(null\) verursacht `printf`\- die Familienfunktionen, um `%n` zu interpretieren, wie in [printf\-Typenfeldzeichen](../../c-runtime-library/printf-type-field-characters.md) beschrieben.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_set_printf_count_output`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_set_printf_count_output.c  
#include <stdio.h>  
  
int main()  
{  
   int e;  
   int i;  
   e = _set_printf_count_output( 1 );  
   printf( "%%n support was %sabled.\n",  
        e ? "en" : "dis" );  
   printf( "%%n support is now %sabled.\n",  
        _get_printf_count_output() ? "en" : "dis" );  
   printf( "12345%n6789\n", &i ); // %n format should set i to 5  
   printf( "i = %d\n", i );  
}  
```  
  
## Ausgabe  
  
```  
%n support was disabled.  
%n support is now enabled.  
123456789  
i = 5  
```  
  
## Entsprechung in .NET Framework  
 Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [\_get\_printf\_count\_output](../../c-runtime-library/reference/get-printf-count-output.md)