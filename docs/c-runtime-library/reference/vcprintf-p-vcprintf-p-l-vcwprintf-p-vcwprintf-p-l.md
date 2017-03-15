---
title: "_vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vcprintf_p"
  - "_vcwprintf_p_l"
  - "_vcprintf_p_l"
  - "_vcwprintf_p"
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
  - "vcwprintf_p"
  - "vcprintf_p_l"
  - "_vcprintf_p"
  - "_vcprintf_p_l"
  - "vcwprintf_p_l"
  - "vcprintf_p"
  - "_vcwprintf_p"
  - "_vcwprintf_p_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vcprintf_p-Funktion"
  - "_vcprintf_p_l-Funktion"
  - "_vcwprintf_p-Funktion"
  - "_vcwprintf_p_l-Funktion"
  - "_vtcprintf_p-Funktion"
  - "_vtcprintf_p_l-Funktion"
  - "vcprintf_p-Funktion"
  - "vcprintf_p_l-Funktion"
  - "vcwprintf_p-Funktion"
  - "vcwprintf_p_l-Funktion"
  - "vtcprintf_p-Funktion"
  - "vtcprintf_p_l-Funktion"
ms.assetid: 611024cc-90e7-41db-8e85-145ca95012b1
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreibt formatierte Ausgabe in die Konsole unter Verwendung eines Zeigers auf eine Liste von Argumenten und unterstützt positionelle Parameter in der Formatzeichenfolge.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _vcprintf_p(  
   const char* format,  
   va_list argptr  
);  
int _vcprintf_p_l(  
   const char* format,  
   locale_t locale,  
   va_list argptr  
);  
int _vcwprintf_p(  
   const wchar_t* format,  
   va_list argptr  
);  
int _vcwprintf_p_l(  
   const wchar_t* format,  
   locale_t locale,  
   va_list argptr  
);  
```  
  
#### Parameter  
 `format`  
 Die Formatangabe.  
  
 `argptr`  
 Ein Zeiger auf eine Liste der Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
 Weitere Informationen finden Sie unter [Syntax der Formatangabe: printf\- und wprintf\-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Rückgabewert  
 Die Anzahl geschriebener Zeichen oder ein negativer Wert im Falle eines Ausgabefehlers.  Wenn `format` ein NULL\-Zeiger ist, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` festgelegt und – 1 zurückgegeben.  
  
## Hinweise  
 Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste und verwendet dann die `_putch` Funktion, um die angegebenen Daten in die Konsole zu formatieren und zu schreiben.  \(`_vcwprintf_p` verwendet `_putwch` anstelle von `_putch`.  `_vcwprintf_p` ist die Breitzeichenversion von `_vcprintf_p`.  Eine Zeichenfolge mit Breitzeichen wird als Argument akzeptiert.\)  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter, der anstelle des aktuellen Gebietsschemas übergeben wurde.  
  
 Jedes `argument` \(falls vorhanden\) wird entsprechend der jeweiligen Formatangabe in `format` konvertiert und ausgegeben.  Die Formatangabe unterstützt positionelle Parameter, damit Sie die Reihenfolge, in der die Argumente verwendet werden, in der Formatzeichenfolge angeben können.  Weitere Informationen finden Sie unter [printf\_p\-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Diese Funktionen übersetzen keine Zeilenvorschubzeichen in Carriage Return\-Zeilenvorschub \(CR\-LF\) Kombinationen bei der Ausgabe.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](security.avoiding_buffer_overruns).  
  
 Diese Funktionen überprüfen den Eingabezeiger und die Formatzeichenfolge.  Wenn `format` oder `argument``NULL` sind, oder wenn die Formatzeichenfolge ungültige Formatierungszeichen enthält, rufen diese Funktionen den Handler für ungültigen Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL` fest.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_vtcprintf_p`|`_vcprintf_p`|`_vcprintf_p`|`_vcwprintf_p`|  
|`_vtcprintf_p_l`|`_vcprintf_p_l`|`_vcprintf_p_l`|`_vcwprintf_p_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_vcprintf_p`, `_vcprintf_p_l`|\<conio.h\> und \<stdarg.h\>|  
|`_vcwprintf_p`, `_vcwprintf_p_l`|\<conio.h\> und \<stdarg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_vcprintf_p.c  
// compile with: /c  
#include <conio.h>  
#include <stdarg.h>  
  
// An error formatting function that's used to print to the console.  
int eprintf(const char* format, ...)  
{  
  va_list args;  
  va_start(args, format);  
  return _vcprintf_p(format, args);  
}  
  
int main()  
{  
   int n = eprintf("parameter 2 = %2$d; parameter 1 = %1$s\r\n",  
      "one", 222);  
   _cprintf_s("%d characters printed\r\n");  
}  
```  
  
  **Parameter 2 \= 222; Parameter 1 \= eins**  
**38 Zeichen gedruckt**   
## Siehe auch  
 [Konsole und Port\-E\/A](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)   
 [printf\_p\-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md)