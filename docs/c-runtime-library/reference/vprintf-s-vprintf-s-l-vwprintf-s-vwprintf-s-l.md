---
title: "vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vwprintf_s_l"
  - "vwprintf_s"
  - "_vprintf_s_l"
  - "vprintf_s"
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
  - "vprintf_s"
  - "vwprintf_s"
  - "_vtprintf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vprintf_s_l-Funktion"
  - "_vtprintf_s-Funktion"
  - "_vtprintf_s_l-Funktion"
  - "_vwprintf_s_l-Funktion"
  - "Formatierter Text [C++]"
  - "vprintf_s-Funktion"
  - "vprintf_s_l-Funktion"
  - "vtprintf_s-Funktion"
  - "vtprintf_s_l-Funktion"
  - "vwprintf_s-Funktion"
  - "vwprintf_s_l-Funktion"
ms.assetid: cf864996-a530-4b40-9c30-54c4cef439c8
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreibt eine formatierte Ausgabe mithilfe eines Zeigers, der auf eine Liste von Argumenten zeigt.  Diese Versionen von [vprintf, \_vprintf\_l, vwprintf, \_vwprintf\_l](../../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
int vprintf_s(  
   const char *format,  
   va_list argptr   
);  
int _vprintf_s_l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int vwprintf_s(  
   const wchar_t *format,  
   va_list argptr   
);  
int _vwprintf_s_l(  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### Parameter  
 `format`  
 Formatangabe.  
  
 `argptr`  
 Zeiger zur Liste der Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
 Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Rückgabewert  
 `vprintf_s` und `vwprintf_s` geben die Anzahl der geschriebenen Zeichen ohne das abschließende Nullzeichen zurück oder einen negativen Wert, wenn ein Ausgabefehler auftritt.  Wenn `format` ein NULL\-Zeiger ist oder wenn Formatzeichenfolge ungültige Formatierungszeichen enthält, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben die Funktionen – 1 zurück und legen `errno` auf `EINVAL` fest.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste und formatiert und schreibt anschließend die vorhandenen Daten in `stdout`.  
  
 Die sicheren Versionen dieser Funktionen unterscheiden sich von `vprintf` und `vwprintf` nur darin, dass die sicheren Versionen überprüfen, ob die Formatzeichenfolge gültige Formatierungszeichen enthält.  
  
 `vwprintf_s` ist die Breitzeichenversion von `vprintf_s`; die zwei Funktionen verhalten sich identisch, wenn der Stream im ANSI\-Modus geöffnet ist.  `vprintf_s` unterstützt derzeit die Ausgabe in einen UNICODE\-Stream nicht.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_vtprintf_s`|`vprintf_s`|`vprintf_s`|`vwprintf_s`|  
|`_vtprintf_s_l`|`_vprintf_s_l`|`_vprintf_s_l`|`_vwprintf_s_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------------|----------------------|  
|`vprintf_s`, `_vprintf_s_l`|\<stdio.h\> und \<stdarg.h\>|\<varargs.h\>\*|  
|`vwprintf_s`, `_vwprintf_s_l`|\<stdio.h\> oder \<wchar.h\> und \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* Benötigt für die Kompatibilität mit UNIX V.  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [vprintf\-Funktionen](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)