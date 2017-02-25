---
title: "strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbstok_l"
  - "_mbstok"
  - "wcstok"
  - "_mbstok"
  - "strtok"
  - "_wcstok_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbstok"
  - "strtok"
  - "_tcstok"
  - "wcstok"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbstok-Funktion"
  - "_mbstok_l-Funktion"
  - "_strtok_l-Funktion"
  - "_tcstok-Funktion"
  - "_tcstok_l-Funktion"
  - "_wcstok_l-Funktion"
  - "mbstok-Funktion"
  - "mbstok_l-Funktion"
  - "Zeichenfolgen [C++], Suchen"
  - "strtok-Funktion"
  - "strtok_l-Funktion"
  - "tcstok-Funktion"
  - "tcstok_l-Funktion"
  - "Token, Suchen in Zeichenfolgen"
  - "wcstok-Funktion"
  - "wcstok_l-Funktion"
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
caps.latest.revision: 34
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 34
---
# strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sucht das nächste Token in einer Zeichenfolge unter Verwendung des angegebenen Gebietsschemas oder eines Gebietsschemas, das übergeben wird.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [strtok\_s, \_strtok\_s\_l, wcstok\_s, \_wcstok\_s\_l, \_mbstok\_s, \_mbstok\_s\_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).  
  
> [!IMPORTANT]
>  `_mbstok` und `_mbstok_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *strtok(  
   char *strToken,  
   const char *strDelimit   
);  
wchar_t *wcstok(  
   wchar_t *strToken,  
   const wchar_t *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `strToken`  
 Zeichenfolge, die mindestens ein Token enthält.  
  
 `strDelimit`  
 Gruppe von Trennzeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Gibt einen Zeiger auf das nächste Token zurück, das in `strToken` gefunden wird.  Wenn keine weiteren Token gefunden werden, wird `NULL` zurückgegeben.  Jeder Aufruf ändert `strToken`, indem er das Trennzeichen, das nach dem zurückgegebenen Token auftritt, durch ein `NULL`\-Zeichen ersetzt.  
  
## Hinweise  
 Die `strtok`\-Funktion sucht das nächste Token in `strToken`.  Der Satz von Zeichen in `strDelimit` gibt mögliche Trennzeichen des in `strToken` gefunden Tokens für den aktuellen Aufruf an.  `wcstok` und `_mbstok` sind Breitzeichen\- und Multibytezeichenversionen von `strtok`.  Die Argumente und der Rückgabewert von `wcstok` sind Breitzeichen\-Zeichenfolgen; die von `_mbstok` sind Mehrbyte\-Zeichenfolgen.  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
> [!IMPORTANT]
>  Diese Funktionen stellen eine mögliche Bedrohung aufgrund eines Pufferüberlaufproblems dar.  Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Beim ersten Aufruf von `strtok` überspringt die Funktion vorangestellte Trennzeichen, gibt einen Zeiger auf das erste Token in `strToken` zurück und beendet das Token mit einem NULL\-Zeichen.  Vom restlichen `strToken` können weitere Token durch mehrere Aufrufe von `strtok` geholt werden.  Jeder Aufruf von `strtok` ändert die `strToken`, mit einem NULL\-Zeichen nach `token` eingefügt, das durch diesen Aufruf zurückgegeben wird.  Um das folgende Token von `strToken` zu lesen, rufen Sie `strtok` auf, und geben Sie dabei einen `NULL`\-Wert für das `strToken`\-Argument an.  Das `NULL` `strToken`\-Argument bewirkt, dass `strtok` im geänderten `strToken` nach dem nächsten Token sucht.  Das `strDelimit`\-Argument kann zwischen zwei Aufrufen jeden beliebigen Wert annehmen, damit der Satz von Trennzeichen variieren kann.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
> [!NOTE]
>  Jede Funktion verwendet eine statische Variable eines lokalen Threads, um die Zeichenfolge in Token zu analysieren.  Daher können mehrere Threads diese Funktionen gleichzeitig aufrufen, ohne dass unerwünschte Auswirkungen auftreten.  Innerhalb eines einzelnen Threads ist es jedoch wahrscheinlich, dass ein überlappendes Aufrufen von einer dieser Funktionen zu Datenbeschädigung und ungenauen Ergebnissen führt.  Beim Analysieren verschiedener Zeichenfolgen sollte zuerst eine Zeichenfolge zu Ende analysiert werden, bevor mit dem Analysieren der nächsten Zeichenfolge begonnen wird.  Berücksichtigen Sie auch das mögliche Risiko, wenn Sie eine dieser Funktionen aus einer Schleife heraus aufrufen, in der eine andere Funktion aufgerufen wird.  Wenn die andere Funktion eine dieser Funktionen verwendet, kommt es zu einer überlappenden Sequenz von Aufrufen und Datenbeschädigung ist die Folge.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcstok`|`strtok`|`_mbstok`|`wcstok`|  
|`_tcstok`|`_strtok_l`|`_mbstok_l`|`_wcstok_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strtok`|\<string.h\>|  
|`wcstok`|\<string.h\> oder \<wchar.h\>|  
|`_mbstok`, `_mbstok_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strtok.c  
// compile with: /W3  
// In this program, a loop uses strtok  
// to print all the tokens (separated by commas  
// or blanks) in the string named "string".  
//  
#include <string.h>  
#include <stdio.h>  
  
char string[] = "A string\tof ,,tokens\nand some  more tokens";  
char seps[]   = " ,\t\n";  
char *token;  
  
int main( void )  
{  
   printf( "Tokens:\n" );  
  
   // Establish string and get the first token:  
   token = strtok( string, seps ); // C4996  
   // Note: strtok is deprecated; consider using strtok_s instead  
   while( token != NULL )  
   {  
      // While there are tokens in "string"  
      printf( " %s\n", token );  
  
      // Get next token:   
      token = strtok( NULL, seps ); // C4996  
   }  
}  
```  
  
  **Tokens:**  
 **A**  
 **string**  
 **von**  
 **tokens**  
 **und**  
 **some**  
 **more**  
 **tokens**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)