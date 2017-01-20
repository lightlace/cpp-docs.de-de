---
title: "gets_s, _getws_s"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_getws_s"
  - "gets_s"
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
  - "_getws_s"
  - "gets_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getws_s-Funktion"
  - "Pufferüberläufe"
  - "Puffer, Vermeiden von Überläufen"
  - "Puffer, Pufferüberläufe"
  - "gets_s-Funktion"
  - "getws_s-Funktion"
  - "Linien, Abrufen"
  - "Standardeingabe, Lesen aus"
  - "Streams, Abrufen von Zeilen"
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
caps.latest.revision: 29
caps.handback.revision: "27"
ms.author: "corob"
manager: "ghogen"
---
# gets_s, _getws_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft eine Zeile aus dem `stdin`\-Stream ab.  Diese Versionen von [gets, \_getws](../../c-runtime-library/gets-getws.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
char *gets_s(   
   char *buffer,  
   size_t sizeInCharacters  
);  
wchar_t *_getws_s(   
   wchar_t *buffer,  
   size_t sizeInCharacters  
);  
template <size_t size>  
char *gets_s(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws_s(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Parameter  
 \[out\] `buffer`  
 Speicherort für die Eingabezeichenfolge.  
  
 \[in\] `sizeInCharacters`  
 Die Größe des Puffers.  
  
## Rückgabewert  
 Gibt bei Erfolg `buffer` zurück.  Ein `NULL`\-Zeiger weist auf einen Fehler oder eine Dateiendebedingung hin.  Verwenden Sie [ferror](../../c-runtime-library/reference/ferror.md) oder [feof](../../c-runtime-library/reference/feof.md), um festzulegen, was aufgetreten ist.  
  
## Hinweise  
 Die `gets_s`\-Funktion liest eine Zeile aus dem Standardeingabestream `stdin` und speichert sie in `buffer`.  Die Zeile enthält alle Zeichen einschließlich des ersten Zeilenumbruchzeichens \('\\n'\).  `gets_s` ersetzt dann das Zeilenumbruchzeichen durch ein NULL\-Zeichen \('\\0'\), ehe die Zeile zurückgegeben wird.  Im Gegensatz dazu behält die `fgets_s`\-Funktion das Zeilenumbruchzeichen bei.  
  
 Wenn das erste gelesene Zeichen das Dateiendezeichen ist, wird ein NULL\-Zeichen am `buffer`\-Anfang gespeichert und `NULL` zurückgegeben.  
  
 `_getws` ist eine Breitzeichenversion von `gets_s`. Das Argument und der Rückgabewert sind Breitzeichen\-Zeichenfolgen.  
  
 Wenn `buffer``NULL` ist oder wenn `sizeInCharacters` kleiner oder gleich null oder wenn der Puffer zu klein für die Eingabezeile und das abschließende NULL\-Zeichen ist, rufen diese Funktionen einen Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `NULL` zurück und setzen "errno" auf `ERANGE`.  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_getts`|`gets_s`|`gets_s`|`_getws`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`gets_s`|\<stdio.h\>|  
|`_getws`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_gets_s.c  
// This program retrieves a string from the stdin and   
// prints the same string to the console.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char line[21]; // room for 20 chars + '\0'  
   gets_s( line, 20 );  
   printf( "The line entered was: %s\n", line );  
}  
```  
  
  **`Hallo Ihr da!`Die eingegebene Zeile lautete: Hello there\!**   
## .NET Framework-Entsprechung  
 [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [gets, \_getws](../../c-runtime-library/gets-getws.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [puts, \_putws](../../c-runtime-library/reference/puts-putws.md)