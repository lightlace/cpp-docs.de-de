---
title: "_cscanf, _cscanf_l, _cwscanf, _cwscanf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cscanf_l"
  - "_cscanf"
  - "_cwscanf"
  - "_cwscanf_l"
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
  - "_cwscanf"
  - "cwscanf_l"
  - "tcscanf_l"
  - "_tcscanf_l"
  - "_cscanf"
  - "_cscanf_l"
  - "tcscanf"
  - "cwscanf"
  - "_cwscanf_l"
  - "cscanf_l"
  - "_tcscanf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cscanf-Funktion"
  - "_cscanf_l-Funktion"
  - "_cwscanf-Funktion"
  - "_cwscanf_l-Funktion"
  - "_tcscanf-Funktion"
  - "_tcscanf_l-Funktion"
  - "cscanf_l-Funktion"
  - "cwscanf-Funktion"
  - "cwscanf_l-Funktion"
  - "Daten [C++], Lesen aus der Konsole"
  - "Lesen von Daten [C++], aus der Konsole"
  - "tcscanf-Funktion"
  - "tcscanf_l-Funktion"
ms.assetid: dbfe7547-b577-4567-a1cb-893fa640e669
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _cscanf, _cscanf_l, _cwscanf, _cwscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest formatierte Daten aus der Konsole.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _cscanf(   
   const char *format [,  
   argument] ...   
);  
int _cscanf_l(   
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _cwscanf(   
   const wchar_t *format [,  
   argument] ...   
);  
int _cwscanf_l(   
   const wchar_t *format,  
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
 Die Anzahl der Felder, die erfolgreich konvertiert und zugewiesen wurden.  Der Rückgabewert enthält keine nicht zugewiesenen gelesenen Felder.  Der Rückgabewert ist `EOF`, wenn versucht wurde, am Dateiende zu lesen.  Dies kann vorkommen, wenn Tastatureingaben auf der Befehlszeilenebene des Betriebssystems umgeleitet wurden.  Ein Rückgabewert von 0 bedeutet, dass keine Felder zugewiesen wurden.  
  
## Hinweise  
 Die `_cscanf`\-Funktion liest Daten direkt aus der Konsole in die Speicherorte, die von `argument` angegeben werden.  Die Funktion [\_getche](../../c-runtime-library/reference/getch-getwch.md) wird verwendet, um Zeichen zu lesen.  Jeder optionaler Parameter muss ein Zeiger auf einen Variablentyp sein, der einem Typspezifizierer in `format` entspricht.  Das Format steuert die Interpretation der Eingabefelder und verfügt über die gleiche Form und Funktion wie der `format`\-Parameter für die [scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)\-Funktion.  Während `_cscanf` normalerweise das Eingabezeichen wiederholt, geschieht dies nicht, wenn zuletzt `_ungetch` aufgerufen wurde.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn "format" NULL ist, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `EOF` zurück.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tcscanf`|`_cscanf`|`_cscanf`|`_cwscanf`|  
|`_tcscanf_l`|`_cscanf_l`|`_cscanf_l`|`_cwscanf_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_cscanf`,`_cscanf_l`|\<conio.h\>|  
|`_cwscanf`, `_cwscanf_l`|\<conio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_cscanf.c  
// compile with: /c /W3  
/* This program prompts for a string  
 * and uses _cscanf to read in the response.  
 * Then _cscanf returns the number of items  
 * matched, and the program displays that number.  
 */  
  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int   result, i[3];  
  
   _cprintf_s( "Enter three integers: ");  
   result = _cscanf( "%i %i %i", &i[0], &i[1], &i[2] ); // C4996  
   // Note: _cscanf is deprecated; consider using _cscanf_s instead  
   _cprintf_s( "\r\nYou entered " );  
   while( result-- )  
      _cprintf_s( "%i ", i[result] );  
   _cprintf_s( "\r\n" );  
}  
```  
  
## Eingabe  
  
```  
1 2 3  
```  
  
## Ausgabe  
  
```  
Enter three integers: 1 2 3  
You entered 3 2 1  
```  
  
## Siehe auch  
 [Konsole und Port\-E\/A](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)