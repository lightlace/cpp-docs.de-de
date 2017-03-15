---
title: "_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cprintf_p_l"
  - "_cwprintf_p_l"
  - "_cwprintf_p"
  - "_cprintf_p"
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
  - "cprintf_p"
  - "cwprintf_p"
  - "tcprintf_p"
  - "_cwprintf_p_l"
  - "_cprintf_p"
  - "csprintf_p_l"
  - "_cprintf_p_l"
  - "_cwprintf_p"
  - "_tcprintf_p"
  - "cprintf_p_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cprintf_p-Funktion"
  - "_cprintf_p_l-Funktion"
  - "_cwprintf_p-Funktion"
  - "_cwprintf_p_l-Funktion"
  - "_tcprintf_p-Funktion"
  - "_tcprintf_p_l-Funktion"
  - "cprintf_p-Funktion"
  - "cprintf_p_l-Funktion"
  - "cwprintf_p-Funktion"
  - "cwprintf_p_l-Funktion"
  - "tcprintf_p-Funktion"
  - "tcprintf_p_l-Funktion"
ms.assetid: 1f82fd7d-13c8-4c4a-a3e4-db0df3873564
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# _cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Formatiert Daten und gibt diese über die Konsole aus und unterstützt positionelle Parameter in der Formatzeichenfolge.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _cprintf_p(   
   const char * format [,   
   argument] ...   
);  
int _cprintf_p_l(   
   const char * format,  
   locale_t locale [,   
   argument] ...   
);  
int _cwprintf_p(  
   const wchar * format [,   
   argument] ...  
);  
int _cwprintf_p_l(  
   const wchar * format,  
   locale_t locale [,  
   argument] ...  
);  
```  
  
#### Parameter  
 `format`  
 Formatsteuerzeichenfolge.  
  
 `argument`  
 Optionale Parameter.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Die Anzahl gedruckter Zeichen oder ein negativer Wert im Falle eines Fehlers.  
  
## Hinweise  
 Diese Funktionen formatieren eine Reihe von Zeichen und Werten und geben diese direkt über die Konsole aus, indem sie die Funktionen `_putch` und `_putwch` für die Zeichenausgabe verwenden.  Jedes `argument` \(falls vorhanden\) wird entsprechend der jeweiligen Formatangabe in `format` konvertiert und ausgegeben.  Das Format hat dieselbe Form und Funktion wie der `format`\-Parameter für die [printf\_p](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)\-Funktion.  Der Unterschied zwischen `_cprintf_p` und `cprintf_s` ist, dass `_cprintf_p` Positionsparameter unterstützt, wodurch festgelegt werden kann, in welcher Reihenfolge die Argumente in der Formatzeichenfolge verwendet werden.  Weitere Informationen finden Sie unter [printf\_p\-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Anders als die `fprintf_p`\-, `printf_p`\- und `sprintf_p`\-Funktionen übersetzen weder `_cprintf_p` noch `_cwprintf_p` Zeilenvorschubzeichen bei der Ausgabe in eine Kombination aus Wagenrücklauf und Zeilenvorschub \(CR\-LF\).  Ein wichtiger Unterschied ist, dass `_cwprintf_p` bei der Verwendung in Windows NT Unicode\-Zeichen anzeigt.  Anders als `_cprintf_p` verwendet `_cwprintf_p` die aktuellen Einstellungen des Konsolengebietsschemas.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist.  
  
 Ebenso wie `_cprintf_s` und `_cwprintf_s` überprüfen sie den Eingabezeiger und die Formatzeichenfolge.  Wenn `format` oder `argument` `NULL` sind, oder wenn die Formatzeichenfolge ungültige Formatierungszeichen enthält, rufen diese Funktionen den Handler für ungültigen Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL` fest.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tcprintf_p`|`_cprintf_p`|`_cprintf_p`|`_cwprintf_p`|  
|`_tcprintf_p_l`|`_cprintf_p_l`|`_cprintf_p_l`|`_cwprintf_p_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_cprintf_p`,`_cprintf_p_l`|\<conio.h\>|  
|`_cwprintf_p`,`_cwprintf_p_l`|\<conio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_cprintf_p.c  
// This program displays some variables to the console  
// using the _cprintf_p function.  
  
#include <conio.h>  
  
int main( void )  
{  
    int         i = -16,  
                h = 29;  
    unsigned    u = 62511;  
    char        c = 'A';  
    char        s[] = "Test";  
  
    // Note that console output does not translate  
    // \n as standard output does. Use \r\n instead.  
    _cprintf_p( "%2$d  %1$.4x  %3$u  %4$c %5$s\r\n",   
                h, i, u, c, s );  
}  
```  
  
  **\-16  001d  62511  Ein Test**   
## Siehe auch  
 [Konsole und Port\-E\/A](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)   
 [\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)   
 [\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)   
 [printf\_p\-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md)   
 [Syntax der Formatangabe: printf\- und wprintf\-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)