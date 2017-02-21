---
title: "_gcvt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gcvt"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_gcvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CVTBUFSIZE"
  - "_gcvt-Funktion"
  - "Konvertierungen, Gleitkommawerte zu Zeichenfolgen"
  - "CVTBUFSIZE"
  - "Gleitkommafunktionen, Konvertieren einer Zahl in eine Zeichenfolge"
  - "gcvt-Funktion"
  - "Zahlen, Konvertieren in Zeichenfolgen"
  - "Zeichenfolgen [C++], Konvertieren aus Gleitkommazahl"
ms.assetid: 5761411e-c06b-409a-912f-810fe7f4bcb5
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _gcvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert einen Gleitkommawert in eine Zeichenfolge, die es in einem Puffer gespeichert werden.  Eine sicherere Version dieser Funktion ist verfügbar; finden Sie unter [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md).  
  
## Syntax  
  
```  
char *_gcvt(   
   double value,  
   int digits,  
   char *buffer   
);  
```  
  
#### Parameter  
 `value`  
 Der zu konvertierende Wert.  
  
 `digits`  
 Anzahl der signifikanten Ziffern gespeichert.  
  
 `buffer`  
 Speicherort für das Ergebnis.  
  
## Rückgabewert  
 `_gcvt` gibt einen Zeiger zur Zeichenfolge aus Ziffern zurück.  
  
## Hinweise  
 Die `_gcvt`\-Funktion konvertiert ein Gleitkommawert `value` als Zeichenfolge \(die ein Dezimaltrennzeichen und ein beliebiges Zeichenbyte enthält\) und die Zeichenfolge in `buffer`.  `buffer` sollte so groß sein, den konvertierten Wert sowie ein NULL anzupassen, das automatisch angefügt wird.  Wenn eine Puffergröße von `digits` \+ 1 verwendet wird, überschreibt die Funktion das Ende des Puffers.  Dies ist, da die konvertierte Zeichenfolge ein Dezimaltrennzeichen enthält und Zeichentasten und Exponenteninformationen enthalten kann.  Es gibt keine Bereitstellung Überläufe.  `_gcvt` versucht, `digits` Ziffern im Dezimalformat zu erzeugen.  Wenn das nicht der Fall ist, erzeugt es `digits` Ziffern im exponentiellen Format.  Nachfolgende Nullen würden in der Konvertierung unterdrückt werden.  
  
 `buffer` der Länge `_CVTBUFSIZE` ist für jeden Gleitkommawert ausreichend.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `buffer` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `NULL` zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_gcvt`|\<stdlib.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_gcvt.c  
// compile with: /W3  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
  
int main( void )  
{  
   char buffer[_CVTBUFSIZE];  
   double value = -1234567890.123;  
   printf( "The following numbers were converted by _gcvt(value,12,buffer):\n" );  
   _gcvt( value, 12, buffer ); // C4996  
   // Note: _gcvt is deprecated; consider using _gcvt_s instead  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
  
   printf( "\n" );  
   value = -12.34567890123;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
}  
```  
  
  **Die folgenden Zahlen wurden durch \_gcvt konvertiert \(Wert, 12, Puffer\):**  
**Puffer: "\- 1234567890,12 " \(char 14\)**  
**Puffer: "\- 12345678901,2 " \(char 14\)**  
**Puffer: "\- 123456789012 " \(char 13\)**  
**Puffer: "\- 1.23456789012e\+012" char \(19\)**  
**Puffer: "\- 12,3456789012 " \(char 14\)**  
**Puffer: "\- 1,23456789012 " \(char 14\)**  
**Puffer: "\- 0,123456789012 " \(char 15\)**  
**Puffer: "\- 1.23456789012e\-002" char \(19\)**   
## .NET Framework-Entsprechung  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)