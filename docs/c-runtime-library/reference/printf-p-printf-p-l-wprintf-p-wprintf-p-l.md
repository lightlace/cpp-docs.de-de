---
title: "_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_printf_p"
  - "_wprintf_p"
  - "_printf_p_l"
  - "_wprintf_p_l"
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
  - "wprintf_p"
  - "_wprintf_p"
  - "printf_p_l"
  - "_printf_p"
  - "printf_p"
  - "_wprintf_p_l"
  - "_printf_p_l"
  - "wprintf_p_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_printf_p-Funktion"
  - "_printf_p_l-Funktion"
  - "_tprintf_p_l-Funktion"
  - "_wprintf_p-Funktion"
  - "_wprintf_p_l-Funktion"
  - "printf_p-Funktion"
  - "printf_p_l-Funktion"
  - "tprintf_p_l-Funktion"
  - "wprintf_p-Funktion"
  - "wprintf_p_l-Funktion"
ms.assetid: 1b7e9ef9-a069-45db-af9d-c2730168322e
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Druckt die formatierte Ausgabe in den Standardausgabestream und ermöglicht die Festlegung der Reihenfolge, in der die Parameter in der Formatzeichenfolge verwendet werden.  
  
## Syntax  
  
```  
int _printf_p(  
   const char *format [,  
   argument]...   
);  
int _printf_p_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int _wprintf_p(  
   const wchar_t *format [,  
   argument]...   
);  
int _wprintf_p_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### Parameter  
 `format`  
 Formatsteuerung  
  
 `argument`  
 Optionale Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Gibt die Anzahl gedruckter Zeichen oder einen negativen Wert zurück, wenn ein Fehler auftritt.  
  
## Hinweise  
 Die `_printf_p` \-Funktion formatiert und druckt eine Reihe von Zeichen und Werten im Standardausgabestream `stdout`.  Wenn Argumente der `format`\-Zeichenfolge folgen, muss die `format`\-Zeichenfolge Spezifikationen enthalten, die das Ausgabeformat der Argumente festlegen \(siehe [printf\_p\-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md)\).  
  
 Der Unterschied zwischen `_printf_p` und `printf_s` ist, dass `_printf_p` positionelle Parameter unterstützt, wodurch festgelegt werden kann, in welcher Reihenfolge die Argumente in der Formatzeichenfolge verwendet werden.  Weitere Informationen finden Sie unter [printf\_p\-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 `_wprintf_p` ist die Breitzeichenversion von `_printf_p`; sie verhalten sich identisch, wenn der Stream im ANSI\-Modus geöffnet wird.  `_printf_p` unterstützt derzeit die Ausgabe in einen UNICODE\-Stream nicht.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist.  
  
 Wenn `format` oder `argument``NULL` sind, oder wenn die Formatzeichenfolge ungültige Formatierungszeichen enthält, rufen die `_printf_p`\- und `_wprintf_p`\-Funktionen einen Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt die Funktion – 1 zurück und stellt `errno` auf `EINVAL` ein.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tprintf_p`|`_printf_p`|`_printf_p`|`_wprintf_p`|  
|`_tprintf_p_l`|`_printf_p_l`|`_printf_p_l`|`_wprintf_p_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_printf_p`, `_printf_p_l`|\<stdio.h\>|  
|`_wprintf_p`, `_wprintf_p_l`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_printf_p.c  
// This program uses the _printf_p and _wprintf_p  
// functions to choose the order in which parameters  
// are used.  
  
#include <stdio.h>  
  
int main( void )  
{  
   // Positional arguments   
   _printf_p( "Specifying the order: %2$s %3$s %1$s %4$s %5$s.\n",  
              "little", "I'm", "a", "tea", "pot");  
  
   // Resume arguments  
   _wprintf_p( L"Reusing arguments: %1$d %1$d %1$d %1$d\n", 10);  
  
   // Width argument  
   _printf_p("Width specifiers: %1$*2$s", "Hello\n", 10);  
}  
```  
  
  **Angeben der Reihenfolge: I'm a little tea pot.**  
**Wiederverwenden von Argumenten: 10 10 10 10**  
**Breitenspezifizierer:     Hello**   
## .NET Framework-Entsprechung  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
-   [System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sprintf\_s, \_sprintf\_s\_l, swprintf\_s, \_swprintf\_s\_l](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)   
 [vprintf\-Funktionen](../../c-runtime-library/vprintf-functions.md)