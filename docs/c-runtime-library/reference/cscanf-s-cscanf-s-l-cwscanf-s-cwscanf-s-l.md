---
title: "_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_cwscanf_s_l"
  - "_cwscanf_s"
  - "_cscanf_s"
  - "_cscanf_s_l"
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
  - "cscanf_s"
  - "cscanf_s_l"
  - "cwscanf_s"
  - "_cwscanf_s"
  - "_tcscanf_s"
  - "_cscanf_s"
  - "_cwscanf_s_l"
  - "_cscanf_s_l"
  - "cwscanf_s_l"
  - "_tcscanf_s_l"
  - "tcscanf_s"
  - "tcscanf_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cscanf_s-Funktion"
  - "_cscanf_s_l-Funktion"
  - "_cwscanf_s-Funktion"
  - "_cwscanf_s_l-Funktion"
  - "_tcscanf_s-Funktion"
  - "_tcscanf_s_l-Funktion"
  - "Konsole [C++], Lesen aus"
  - "cscanf_s-Funktion"
  - "cscanf_s_l-Funktion"
  - "cwscanf_s-Funktion"
  - "cwscanf_s_l-Funktion"
  - "Daten [C++], Lesen aus der Konsole"
  - "Lesen von Daten [C++], aus der Konsole"
  - "tcscanf_s-Funktion"
  - "tcscanf_s_l-Funktion"
ms.assetid: 9ccab74d-916f-42a6-93d8-920525efdf4b
caps.latest.revision: 24
caps.handback.revision: "24"
ms.author: "corob"
manager: "ghogen"
---
# _cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest formatierte Daten aus der Konsole.  Diese sichere Versionen von [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _cscanf_s(   
   const char *format [,  
   argument] ...   
);  
int _cscanf_s_l(   
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _cwscanf_s(   
   const wchar_t *format [,  
   argument] ...   
);  
int _cwscanf_s_l(   
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
  
 Diese Funktionen überprüfen ihre Parameter.  Wenn `format` ein NULL\-Zeiger ist, dann rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, wird diese Rückhol\- Funktionen `EOF` und `errno` auf `EINVAL` festgelegt.  
  
## Hinweise  
 Die `_cscanf_s`\-Funktion liest Daten direkt aus der Konsole in die Speicherorte, die von `argument` angegeben werden.  Die Funktion [\_getche](../../c-runtime-library/reference/getch-getwch.md) wird verwendet, um Zeichen zu lesen.  Jeder optionaler Parameter muss ein Zeiger auf einen Variablentyp sein, der einem Typspezifizierer in `format` entspricht.  Das Format steuert die Interpretation der Eingabefelder und verfügt über das gleiche Formular und die gleiche Funktion wie der `format`\-Parameter für die [scanf\_s](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)\-Funktion.  Während `_cscanf_s` normalerweise das Eingabezeichen wiederholt, geschieht dies nicht, wenn zuletzt `_ungetch` aufgerufen wurde.  
  
 Wie andere sichere Versionen von Funktionen in der `scanf` \- Familie, erfordern `_cscanf_s` und `_cswscanf_s` Größenargumente für die Typfeldzeichen `c`, `C`, `s`, `S` und `[`.  Weitere Informationen finden Sie unter [scanf\-Breitenangabe](../../c-runtime-library/scanf-width-specification.md).  
  
> [!NOTE]
>  Der Größenparameter ist vom Typ `unsigned` und nicht vom Typ `size_t`.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tcscanf_s`|`_cscanf_s`|`_cscanf_s`|`_cwscanf_s`|  
|`_tcscanf_s_l`|`_cscanf_s_l`|`_cscanf_s_l`|`_cwscanf_s_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_cscanf_s`,`_cscanf_s_l`|\<conio.h\>|  
|`_cwscanf_s`, `_cwscanf_s_l`|\<conio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_cscanf_s.c  
// compile with: /c  
/* This program prompts for a string  
 * and uses _cscanf_s to read in the response.  
 * Then _cscanf_s returns the number of items  
 * matched, and the program displays that number.  
 */  
  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int result, n[3];  
   int i;  
  
   result = _cscanf_s( "%i %i %i", &n[0], &n[1], &n[2] );  
   _cprintf_s( "\r\nYou entered " );  
   for( i=0; i<result; i++ )  
      _cprintf_s( "%i ", n[i] );  
   _cprintf_s( "\r\n" );  
}  
```  
  
## Eingabe  
  
```  
1 2 3  
```  
  
## Ausgabe  
  
```  
You entered 1 2 3  
```  
  
## Siehe auch  
 [Konsole und Port\-E\/A](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)