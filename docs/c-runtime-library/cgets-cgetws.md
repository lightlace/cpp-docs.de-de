---
title: "_cgets, _cgetws"
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
  - "_cgetws"
  - "_cgets"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "cgetws"
  - "_cgetws"
  - "_cgets"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cgets-Funktion"
  - "_cgetws-Funktion"
  - "cgets-Funktion"
  - "cgetws-Funktion"
  - "Konsole, Abrufen von Zeichenfolgen aus"
  - "Zeichenfolgen [C++], Abrufen aus Konsole"
ms.assetid: 4d5e134a-58c3-4f62-befd-5d235b0212f4
caps.latest.revision: 32
caps.handback.revision: "32"
ms.author: "corob"
manager: "ghogen"
---
# _cgets, _cgetws
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft eine Zeichenfolge aus der Konsole ab. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_cgets\_s, \_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
> [!IMPORTANT]
>  Diese Funktionen sind veraltet. Von Visual Studio 2015 an sind sie nicht in der CRT verfügbar. Dies sicheren Versionen dieser Funktionen, „\_cgets\_s“ und „\_cgetws\_s“, stehen noch zur Verfügung. Informationen zu diesen alternativen Funktionen finden Sie unter [\_cgets\_s, \_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In \/ZW nicht unterstützte CRT\-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *_cgets(   
   char *buffer   
);  
wchar_t *_cgetws(  
   wchar_t *buffer  
);  
template <size_t size>  
char *_cgets(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_cgetws(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Parameter  
 `buffer`  
 Speicherort für Daten.  
  
## Rückgabewert  
 `_cgets` und `_cgetws` geben bei `buffer[2]` einen Zeiger auf den Anfang der Zeichenfolge zurück. Wenn `buffer``NULL` ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `NULL` zurückgegeben und `errno` auf `EINVAL` festgelegt.  
  
## Hinweise  
 Diese Funktionen lesen eine Zeichenfolge von der Konsole und speichern die Zeichenfolge und ihre Länge im Speicherort, auf den `buffer` zeigt. Der`buffer`\-Parameter muss ein Zeiger auf ein Zeichenarray sein.`buffer[0]`, das erste Element des Arrays, muss die maximale Länge \(in Zeichen\) der zu lesenden Zeichenfolge enthalten. Das Array muss genügend Elemente enthalten, um die Zeichenfolge, ein abschließendes Nullzeichen \('\\0'\) und zwei zusätzliche Bytes einzuschließen. Die Funktion liest die Zeichen bis zu einer Kombination aus Wagenrücklauf und Zeilenvorschub \(CR\-LF\) oder bis die angegebene Anzahl von Zeichen gelesen ist. Die Zeichenfolge wird ab `buffer[2]` gespeichert. Wenn die Funktion ein CR\-LF liest, speichert sie das NULL\-Zeichen \('\\0'\). Die Funktion speichert dann im zweiten Arrayelement `buffer[1]` die tatsächliche Länge der Zeichenfolge.  
  
 Da alle Bearbeitungsschlüssel aktiv sind, wenn `_cgets` oder`_cgetws` in einem Konsolenfenster aufgerufen wird, wird durch Drücken der F3\-TASTE der letzte eingegebene Eintrag wiederholt.  
  
 In C\+\+ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_cgetts`|`_cgets`|`_cgets`|`_cgetws`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_cgets`|\<conio.h\>|  
|`_cgetws`|\<conio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_cgets.c // compile with: /c /W3 // This program creates a buffer and initializes // the first byte to the size of the buffer. Next, the // program accepts an input string using _cgets and displays // the size and text of that string. #include <conio.h> #include <stdio.h> #include <errno.h> int main( void ) { char buffer[83] = { 80 };  // Maximum characters in 1st byte char *result; printf( "Input line of text, followed by carriage return:\n"); // Input a line of text: result = _cgets( buffer ); // C4996 // Note: _cgets is deprecated; consider using _cgets_s if (!result) { printf( "An error occurred reading from the console:" " error code %d\n", errno); } else { printf( "\nLine length = %d\nText = %s\n", buffer[1], result ); } }  
```  
  
```Output  
  
A line of input.Eingabezeile mit Text, gefolgt von einem Wagenrücklauf: Zeilenlänge = 19 Text = Eine Zeile Eingabe.  
```  
  
## Siehe auch  
 [Konsole und Port\-E\/A](../c-runtime-library/console-and-port-i-o.md)   
 [\_getch, \_getwch](../c-runtime-library/reference/getch-getwch.md)