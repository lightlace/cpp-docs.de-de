---
title: "Analysieren von C-Befehlszeilenargumenten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Befehlszeile, Analysieren"
  - "Doppelte Anführungszeichen"
  - "Analysieren, Befehlszeilenargumente"
  - "Anführungszeichen, Befehlszeilenargumente"
  - "Startcode, Analysieren von Befehlszeilenargumenten"
ms.assetid: ffce8037-2811-45c4-8db4-1ed787859c80
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Analysieren von C-Befehlszeilenargumenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Beim Interpretieren von Argumenten, die in der Befehlszeile des Betriebssystems angegeben werden, verwendet der Microsoft C\-Startcode die folgenden Regeln:  
  
-   Argumente werden durch einen Leerraum \(Leerzeichen oder Tabstopp\) abgegrenzt.  
  
-   Eine in doppelte Anführungszeichen eingeschlossene Zeichenfolge wird als einzelnes Argument interpretiert, auch wenn darin Leerzeichen enthalten sind.  Eine Zeichenfolge in Anführungszeichen kann in ein Argument eingebettet sein.  Beachten Sie, dass die Einfügemarke \(**^**\) nicht als Escape\- oder Trennzeichen erkannt wird.  
  
-   Wenn dem Anführungszeichen ein umgekehrter Schrägstrich vorangestellt wird \(**\\"**\), wird diese Zeichenfolge als literales Anführungszeichen \(**"**\) interpretiert.  
  
-   Ein umgekehrter Schrägstrich wird als solcher interpretiert, sofern er nicht unmittelbar vor einem Anführungszeichen steht.  
  
-   Wenn ein doppeltes Anführungszeichen auf eine gerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche \(**\\\\**\) ein umgekehrter Schrägstrich \(**\\**\) im `argv`\-Array platziert. Das doppelte Anführungszeichen \(**"**\) wird als Zeichenfolgentrennzeichen interpretiert.  
  
-   Wenn ein doppeltes Anführungszeichen auf eine ungerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche \(**\\\\**\) ein umgekehrter Schrägstrich \(**\\**\) im `argv`\-Array platziert. Das doppelte Anführungszeichen wird vom verbleibenden umgekehrten Schrägstrich als Escapezeichen interpretiert, sodass ein literales Anführungszeichen \(**"**\) in `argv` platziert wird.  
  
 Diese Liste veranschaulicht die zuvor genannten Regeln anhand der an `argv` übergebenen interpretierten Ergebnisse für einige beispielhafte Befehlszeilenargumente.  Die Ausgabe in der zweiten, dritten und vierten Spalte stammt aus dem ARGS.C\-Programm, das auf die Liste folgt.  
  
|Befehlszeileneingabe|argv\[1\]|argv\[2\]|argv\[3\]|  
|--------------------------|---------------|---------------|---------------|  
|`"a b c" d e`|`a b c`|`d`|`e`|  
|`"ab\"c" "\\" d`|`ab"c`|`\`|`d`|  
|`a\\\b d"e f"g h`|`a\\\b`|`de fg`|`h`|  
|`a\\\"b c d`|`a\"b`|`c`|`d`|  
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|  
  
## Beispiel  
  
### Code  
  
```  
// Parsing_C_Commandline_args.c  
// ARGS.C illustrates the following variables used for accessing  
// command-line arguments and environment variables:  
// argc  argv  envp  
//  
  
#include <stdio.h>  
  
int main( int argc, // Number of strings in array argv  
 char *argv[],      // Array of command-line argument strings  
 char **envp )      // Array of environment variable strings  
{  
    int count;  
  
    // Display each command-line argument.  
    printf_s( "\nCommand-line arguments:\n" );  
    for( count = 0; count < argc; count++ )  
        printf_s( "  argv[%d]   %s\n", count, argv[count] );  
  
    // Display each environment variable.  
    printf_s( "\nEnvironment variables:\n" );  
    while( *envp != NULL )  
        printf_s( "  %s\n", *(envp++) );  
  
    return;  
}  
```  
  
## Kommentare  
 Ein Beispiel für die Ausgabe dieses Programms ist:  
  
```  
Command-line arguments:  
  argv[0]   C:\MSC\TEST.EXE  
  
Environment variables:  
  COMSPEC=C:\NT\SYSTEM32\CMD.EXE  
  
  PATH=c:\nt;c:\binb;c:\binr;c:\nt\system32;c:\word;c:\help;c:\msc;c:\;  
  PROMPT=[$p]   
  TEMP=c:\tmp  
  TMP=c:\tmp  
  EDITORS=c:\binr  
  WINDIR=c:\nt        
```  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [main\-Funktion und Programmausführung](../c-language/main-function-and-program-execution.md)