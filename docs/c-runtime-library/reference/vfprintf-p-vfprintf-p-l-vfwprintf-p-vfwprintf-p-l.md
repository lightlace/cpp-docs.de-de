---
title: "_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vfprintf_p"
  - "_vfwprintf_p"
  - "_vfprintf_p_l"
  - "_vfwprintf_p_l"
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
  - "_vfwprintf_p_l"
  - "_vfprintf_p"
  - "vfwprintf_p_l"
  - "vfwprintf_p"
  - "vfprintf_p_l"
  - "_vfwprintf_p"
  - "_vftprintf_p"
  - "_vfprintf_p_l"
  - "vfprintf_p"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vfprintf_p-Funktion"
  - "_vfprintf_p_l-Funktion"
  - "_vftprintf_p-Funktion"
  - "_vftprintf_p_l-Funktion"
  - "_vfwprintf_p-Funktion"
  - "_vfwprintf_p_l-Funktion"
  - "Formatierter Text [C++]"
  - "vfprintf_p-Funktion"
  - "vfprintf_p_l-Funktion"
  - "vftprintf_p-Funktion"
  - "vftprintf_p_l-Funktion"
  - "vfwprintf_p-Funktion"
  - "vfwprintf_p_l-Funktion"
ms.assetid: 4d4a0914-4175-4b65-9ca1-037c4ef29147
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

zum formatierten Ausgabe mithilfe eines Zeigers auf eine Liste mit Argumenten, mit der Möglichkeit, die Reihenfolge anzugeben, ob Argumente in der Formatzeichenfolge verwendet werden.  
  
## Syntax  
  
```  
int _vfprintf_p(  
   FILE *stream,  
   const char *format,  
   va_list argptr   
);  
int _vfprintf_p_l(  
   FILE *stream,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vfwprintf_p(  
   FILE *stream,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vfwprintf_p_l(  
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
 `format`  
 Formatangabe.  
  
 `argptr`  
 Zeiger zur Liste der Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
 Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Rückgabewert  
 `_vfprintf_p` und `_vfwprintf_p` geben die Anzahl der geschriebenen Zeichen ohne das abschließende Nullzeichen zurück oder einen negativen Wert, wenn ein Ausgabefehler auftritt.  
  
## Hinweise  
 Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste und formatiert und schreibt anschließend die vorhandenen Daten in `stream`.  Diese Funktionen unterscheiden sich von `_vfprint_s` und `_vfwprint_s`\-Versionen nur darin, dass sie positionelle Parameter unterstützen.  Weitere Informationen finden Sie unter [printf\_p\-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 `_vfwprintf_p` ist die Breitzeichenversion von `_vprintf_p`; die zwei Funktionen verhalten sich identisch, wenn der Stream im ANSI\-Modus geöffnet ist.  `_vprintf_p` unterstützt derzeit die Ausgabe in einen UNICODE\-Stream nicht.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Wenn entweder `stream` oder `format` ein NULL\-Zeiger ist oder wenn Formatzeichenfolge die ungültige Formatierungszeichen enthält, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben die Funktionen – 1 zurück und legen `errno` auf `EINVAL` fest.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_vftprintf_p`|`_vfprintf_p`|`_vfprintf_p`|`_vfwprintf_p`|  
|`_vftprintf_p_l`|`_vfprintf_p_l`|`_vfprintf_p_l`|`_vfwprintf_p_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------------|----------------------|  
|`_vfprintf_p`, `_vfprintf_p_l`|\<stdio.h\> und \<stdarg.h\>|\<varargs.h\>\*|  
|`_vfwprintf_p`, `_vfwprintf_p_l`|\<stdio.h\> oder \<wchar.h\> und \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* Benötigt für die Kompatibilität mit UNIX V.  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [vprintf\-Funktionen](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)   
 [printf\_p\-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [\_vsprintf\_p, \_vsprintf\_p\_l, \_vswprintf\_p, \_vswprintf\_p\_l](../../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)   
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)