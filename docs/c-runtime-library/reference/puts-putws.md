---
title: "puts, _putws | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_putws"
  - "puts"
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
  - "_putts"
  - "_putws"
  - "puts"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_putts-Funktion"
  - "_putws-Funktion"
  - "puts-Funktion"
  - "putts-Funktion"
  - "putws-Funktion"
  - "Standardausgabe, Schreiben in"
  - "Zeichenfolgen [C++], Schreiben"
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# puts, _putws
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreibt eine Zeichenfolge in **stdout**.  
  
## Syntax  
  
```  
  
      int puts(  
   const char *str   
);  
int _putws(  
   const wchar_t *str   
);  
```  
  
#### Parameter  
 `str`  
 Ausgabezeichenfolge.  
  
## Rückgabewert  
 Gibt bei Erfolg einen nicht negativen Wert zurück.  Wenn `puts` fehlschläft, wird `EOF` zurückgegeben; wenn `_putws` fehlschlägt, wird **WEOF** zurückgegeben.  Wenn `str` ein NULL\-Zeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, setzen die Funktionen `errno` auf `EINVAL` und geben `EOF` oder **WEOF** zurück.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `puts`\-Funktion schreibt `str` in den Standardausgabestream **stdout** und ersetzt das abschließende NULL\-Zeichen \('\\0'\) im Ausgabestream durch ein Zeilenumbruchzeichens \('\\n'\).  
  
 `_putws` ist die Breitzeichenversion von `puts`; die zwei Funktionen verhalten sich identisch, wenn der Stream im ANSI\-Modus geöffnet ist.  `puts` unterstützt derzeit die Ausgabe in einen UNICODE\-Stream nicht.  
  
 In Windows 2000 und höher erstellt **\_putwch** Unicode\-Zeichen mit der aktuellen Einstellung des Konsolengebietsschemas.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_putts`|`puts`|`puts`|`_putws`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`puts`|\<stdio.h\>|  
|`_putws`|\<stdio.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_puts.c  
/* This program uses puts to write a string to stdout.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   puts( "Hello world from puts!" );  
}  
```  
  
## Ausgabe  
  
```  
Hello world from puts!  
```  
  
## .NET Framework-Entsprechung  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)