---
title: "to-Funktionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "To"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Groß- und Kleinschreibung, Konvertieren"
  - "Zeichen, Konvertieren"
  - "Kleinbuchstaben, Konvertieren von Zeichenfolgen"
  - "Zeichenfolgenkonvertierung, Groß- und Kleinschreibung"
  - "Zeichenfolgenkonvertierung, in verschiedene Zeichen"
  - "zu Funktionen"
  - "Großbuchstaben, Konvertieren von Zeichenfolgen"
ms.assetid: f636a4c6-8c9f-4be2-baac-064f9dbae300
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# to-Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jedes der **bis**\-Funktionen und des zugeordneten Makros konvertiert ggf. ein einzelnes Zeichen zu einem anderen Zeichen.  
  
|||  
|-|-|  
|[\_\_toascii](../c-runtime-library/reference/toascii-toascii.md)|[toupper, \_toupper, towupper](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|  
|[tolower, \_tolower, towlower](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)||  
  
## Hinweise  
 Die **bis**\-Funktionen und die Makrokonvertierungen sind wie folgt.  
  
|Routine|Makro|**Beschreibung**|  
|-------------|-----------|----------------------|  
|`__toascii`|`__toascii`|Konvertiert `c` auf ASCII\-Zeichen|  
|`tolower`|`tolower`|Konvertiert `c` in Kleinbuchstaben, bei Bedarf|  
|`_tolower`|`_tolower`|Konvertiert `c` in Kleinbuchstaben|  
|`towlower`|Kein|Konvertiert `c` in den entsprechenden Breitzeichenkleinbuchstaben|  
|`toupper`|`toupper`|Konvertiert `c` in einen Großbuchstaben konvertiert, bei Bedarf|  
|`_toupper`|`_toupper`|Konvertiert `c` in Großbuchstaben|  
|`towupper`|Kein|Konvertiert c zum entsprechenden Breitzeichengroßbuchstaben|  
  
 Um die Funktionsversionen der **bis** Routinen zu verwenden die auch als Makros, entweder definierten entfernen Sie die Makrodefinitionen mit `#undef`\-Direktive oder schließen Sie nicht CTYPE.H. ein.  Wenn die Compileroption \/Za\- verwenden, verwendet der Compiler die Funktionsversion von `toupper` oder `tolower`.  Deklarationen der Funktionen `toupper` und `tolower` sind in STDLIB.H.  
  
 Die Routine `__toascii` legt die abgesehen niedrigwertigen 7 Bits von `c` auf 0 fest, sodass der konvertierte Wert ein Zeichen im ASCII\-Zeichensatz darstellt.  Wenn `c` bereits ein ASCII\-Zeichen darstellt, ist `c` unverändert.  
  
 Die Routinen `tolower` und `toupper`:  
  
-   Stellen Sie in der Kategorie `LC_CTYPE` des aktuellen Gebietsschemas abhängig \(`tolower` ruft `isupper` auf und `toupper` ruft `islower`\) auf.  
  
-   Konvertieren Sie `c`, wenn `c` einen konvertierbaren Buchstaben des entsprechenden Umwandlung im aktuellen Gebietsschema darstellt und der entgegengesetzte Fall für dieses Gebietsschema vorhanden ist.  Andernfalls ist `c` unverändert.  
  
 Die Routinen `_tolower` und `_toupper`:  
  
-   Im gebietsschemaunabhängige, viel höhere Versionen von `tolower` und **toupper.**  
  
-   Kann verwendet werden, wenn **isascii\(**`c`**\)** und **isupper\(**`c`**\)** bzw. **islower\(**`c`**\)** ungleich 0 \(null\) sind.  
  
-   Haben der Ergebnisse undefiniert, wenn `c` kein ASCII\-Buchstabe des entsprechenden Arguments zur Konvertierung ist.  
  
 Die Funktionen `towlower` und `towupper` Geben einer konvertierten Kopie von `c` wenn zurück und wenn beiden folgenden Bedingungen ungleich 0 \(null\) sind.  Andernfalls ist `c` unverändert.  
  
-   `c` ist ein Breitzeichen des entsprechenden Umwandlung \(das heißt, für welches, `iswupper` oder **iswlower,** bzw., nicht 0 ist\).  
  
-   Es ist ein entsprechendes Breitzeichen des Zielfalles, also für, welche `iswlower` oder **iswupper,** bzw., nicht 0 ist\).  
  
## Beispiel  
  
```  
// crt_toupper.c  
/* This program uses toupper and tolower to  
 * analyze all characters between 0x0 and 0x7F. It also  
 * applies _toupper and _tolower to any code in this  
 * range for which these functions make sense.  
 */  
  
#include <ctype.h>  
#include <string.h>  
  
char msg[] = "Some of THESE letters are Capitals.";  
char *p;  
  
int main( void )  
{  
   printf( "%s\n", msg );  
  
   /* Reverse case of message. */  
   for( p = msg; p < msg + strlen( msg ); p++ )  
   {  
      if( islower( *p ) )  
         putchar( _toupper( *p ) );  
      else if( isupper( *p ) )  
         putchar( _tolower( *p ) );  
      else  
         putchar( *p );  
   }  
}  
```  
  
  **Einige DIESER Buchstaben sind Großbuchstaben.**  
**einige dieser BUCHSTABEN SIND Großbuchstaben.**   
## Siehe auch  
 [Datenkonvertierung](../c-runtime-library/data-conversion.md)   
 [Locale](../c-runtime-library/locale.md)   
 [is\- und isw\-Routinen](../c-runtime-library/is-isw-routines.md)