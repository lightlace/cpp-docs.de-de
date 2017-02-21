---
title: "_getche, _getwche | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getwche"
  - "_getche"
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
  - "getwche"
  - "_getche"
  - "_getwche"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_getche-Funktion"
  - "_getwche-Funktion"
  - "Zeichen, Abrufen aus Konsole"
  - "Konsole, Lesen aus"
  - "getche-Funktion"
  - "getwche-Funktion"
ms.assetid: eac978a8-c43a-4130-938f-54f12e2a0fda
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _getche, _getwche
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft ein Zeichen aus der Konsole ab und wiederholt es.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _getche( void );  
wint_t _getwche( void );  
```  
  
## Rückgabewert  
 Gibt das gelesene Zeichen zurück.  Es gibt keine Fehlerrückgabe.  
  
## Hinweise  
 Die Funktionen `_getche` und `_getwche` lesen ein einzelnes Zeichen aus der Konsole mit Wiederholung ab. Das heißt, dass das Zeichen an der Konsole angezeigt wird.  Mit keiner dieser Funktionen kann STRG\+C gelesen werden.  Beim Lesen einer Steuertaste oder einer Pfeiltaste muss jede Funktion zweimal aufgerufen werden. Der erste Aufruf gibt 0 oder 0xE0 und der zweite Aufruf den tatsächlichen Tastencode zurück.  
  
 Diese Funktionen sperren den aufrufenden Thread und sind daher threadsicher.  Informationen zu nicht sperrenden Versionen finden Sie unter [\_getche\_nolock, \_getwche\_nolock](../../c-runtime-library/reference/getche-nolock-getwche-nolock.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_getche`|`_getche`|`_getch`|`_getwche`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_getche`|\<conio.h\>|  
|`_getwche`|\<conio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_getche.c  
// compile with: /c  
// This program reads characters from  
// the keyboard until it receives a 'Y' or 'y'.  
  
#include <conio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
  
   _cputs( "Type 'Y' when finished typing keys: " );  
   do  
   {  
      ch = _getche();  
      ch = toupper( ch );  
   } while( ch != 'Y' );  
  
   _putch( ch );  
   _putch( '\r' );    // Carriage return  
   _putch( '\n' );    // Line feed       
}  
```  
  
  **`abcdey`Geben Sie "Y" ein, wenn Sie die Tastatureingabe beendet haben: Y**   
## Entsprechung in .NET Framework  
 Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Konsole und Port\-E\/A](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cgets, \_cgetws](../../c-runtime-library/cgets-cgetws.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [\_ungetch, \_ungetwch, \_ungetch\_nolock, \_ungetwch\_nolock](../../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)