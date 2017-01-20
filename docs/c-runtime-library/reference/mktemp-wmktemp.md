---
title: "_mktemp, _wmktemp"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_wmktemp"
  - "_mktemp"
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
  - "_tmktemp"
  - "wmktemp"
  - "tmktemp"
  - "_wmktemp"
  - "_mktemp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mktemp-Funktion"
  - "_tmktemp-Funktion"
  - "_wmktemp-Funktion"
  - "Dateien [C++], Temporär"
  - "mktemp-Funktion"
  - "Temporäre Dateien [C++]"
  - "tmktemp-Funktion"
  - "wmktemp-Funktion"
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
caps.latest.revision: 25
caps.handback.revision: "23"
ms.author: "corob"
manager: "ghogen"
---
# _mktemp, _wmktemp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt einen eindeutigen Dateinamen.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_mktemp\_s, \_wmktemp\_s](../../c-runtime-library/reference/mktemp-s-wmktemp-s.md).  
  
## Syntax  
  
```  
char *_mktemp(  
   char *template   
);  
wchar_t *_wmktemp(  
   wchar_t *template   
);  
template <size_t size>  
char *_mktemp(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wmktemp(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### Parameter  
 `template`  
 Dateinamenmuster.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf die geänderte Vorlage zurück.  Die Funktion gibt `NULL` zurück, wenn der `template` NULL ist, oder keine eindeutigen Namen aus der angegebenen Vorlage erstellt werden können.  
  
## Hinweise  
 Die Funktion `_mktemp` erstellt einen eindeutigen Dateinamen, indem das Argument `template` ändert.  `_mktemp` behandelt automatisch Mehrbyte\-Zeichenfolgen\-Argumente entsprechend und derzeit erkennt Mehrbytezeichensequenzen entsprechend der Mehrbyte\-Codepage vom Laufzeitsystem.  `_wmktemp` ist eine Breitzeichenversion von `_mktemp`. Das Argument und der Rückgabewert von `_wmktemp` sind Zeichenfolgen mit Breitzeichen.  `_wmktemp` und `_mktemp` identisch verhalten sich andernfalls, dass `_wmktemp` nicht behandelt Mehrbyte\-Zeichenfolgen.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tmktemp`|`_mktemp`|`_mktemp`|`_wmktemp`|  
  
 Das Argument `template` hat die Form `base` XXXXXX, wobei `base` den Teil des neuen Dateinamen ist, den Sie bereitstellen und jedes X ist ein Platzhalter für ein Zeichen, das von `_mktemp` angegeben wird.  Jedes Platzhalterzeichen in `template` muss einem Großbuchstaben X. sein.  `_mktemp` verwaltet `base` bei und ersetzt das erste schleppende X durch ein alphabetisches Zeichen.  `_mktemp` ersetzt folgenden nachfolgenden Xs durch einen fünfstelligen Wert; Dieser Wert ist eine eindeutige Zahl, die den aufrufenden Prozesses oder in Multithreadprogrammen, der aufrufende Thread gekennzeichnet.  
  
 Jeder erfolgreichen Aufruf von  `_mktemp` ändert `template`.  In jedem nachfolgenden Aufrufs vom selben Prozess oder der Thread mit demselben `template`\-Argument, `_mktemp` Überprüfungen für Dateinamen, dass Abgleichungsnamen durch `_mktemp` in vorherigen Aufrufen zurückkehrten.  Wenn keine Datei für einen angegebenen Namen vorhanden ist, die `_mktemp` zurückgibt, benennen.  Wenn Dateien für alle vorher zurückgegebenen Namen vorhanden, erstellt `_mktemp` einen neuen Namen, indem das alphabetisches Zeichen, das er im zuvor zurückgegebenen Namen mit dem nächsten verfügbaren Kleinbuchstaben verwendete, in der Reihenfolge, von "a" bis "z".  Wenn `base` ist:  
  
```  
fn  
```  
  
 und der fünfstellige Wert, der von `_mktemp` angegeben wird, ist der zurückgegebene 12345, Vorname ist:  
  
```  
fna12345  
```  
  
 Wenn dieser Name verwendet wird, um FNA12345 Datei erstellen und diese Datei vorhanden ist, ist der folgende Name, der in einem Aufruf aus den gleichen Prozess oder Thread mit gleichem `base` für `template` zurückgegeben wird:  
  
```  
fnb12345  
```  
  
 Wenn FNA12345 nicht vorhanden ist, ist der zurückgegebene folgende Namen erneut:  
  
```  
fna12345  
```  
  
 `_mktemp` kann maximal 26 eindeutige Dateinamen für eine bestimmte Kombination von Basis\- und Vorlagenwerten erstellen.  Daher ist FNZ12345 der letzte eindeutige Dateiname `_mktemp` kann für `base` erstellen und `template` beschränkt wird in diesem Beispiel.  
  
 Bei einem Fehler wird `errno` festgelegt.  Wenn `template` ein ungültiges Format \(beispielsweise, weniger als 6 Xs\) aufweist, wird `errno` auf `EINVAL` festgelegt.  Wenn `_mktemp` nicht möglich ist, einen eindeutigen Namen zu erstellen, da alle 26 möglichen Dateinamen bereits vorhanden sind, legt `_mktemp` Vorlage auf eine leere Zeichenfolge festgelegt und `EEXIST` zurückgegeben.  
  
 In C\+\+ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mktemp`|\<io.h\>|  
|`_wmktemp`|\<io.h oder\> wchar.h \<\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_mktemp.c  
// compile with: /W3  
/* The program uses _mktemp to create  
 * unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
#include <errno.h>  
  
char *template = "fnXXXXXX";  
char *result;  
char names[27][9];  
  
int main( void )  
{  
   int i;  
   FILE *fp;  
  
   for( i = 0; i < 27; i++ )  
   {  
      strcpy_s( names[i], sizeof( names[i] ), template );  
      /* Attempt to find a unique filename: */  
      result = _mktemp( names[i] );  // C4996  
      // Note: _mktemp is deprecated; consider using _mktemp_s instead  
      if( result == NULL )  
      {  
         printf( "Problem creating the template\n" );  
         if (errno == EINVAL)  
         {  
             printf( "Bad parameter\n");  
         }  
         else if (errno == EEXIST)  
         {  
             printf( "Out of unique filenames\n");   
         }  
      }  
      else  
      {  
         fopen_s( &fp, result, "w" );  
         if( fp != NULL )  
            printf( "Unique filename is %s\n", result );  
         else  
            printf( "Cannot open %s\n", result );  
         fclose( fp );  
      }  
   }  
}  
```  
  
  **Eindeutiger Dateiname ist fna03912**  
**Eindeutiger Dateiname ist fnb03912**  
**Eindeutiger Dateiname ist fnc03912**  
**Eindeutiger Dateiname ist fnd03912**  
**Eindeutiger Dateiname ist fne03912**  
**Eindeutiger Dateiname ist fnf03912**  
**Eindeutiger Dateiname ist fng03912**  
**Eindeutiger Dateiname ist fnh03912**  
**Eindeutiger Dateiname ist fni03912**  
**Eindeutiger Dateiname ist fnj03912**  
**Eindeutiger Dateiname ist fnk03912**  
**Eindeutiger Dateiname ist fnl03912**  
**Eindeutiger Dateiname ist fnm03912**  
**Eindeutiger Dateiname ist fnn03912**  
**Eindeutiger Dateiname ist fno03912**  
**Eindeutiger Dateiname ist fnp03912**  
**Eindeutiger Dateiname ist fnq03912**  
**Eindeutiger Dateiname ist fnr03912**  
**Eindeutiger Dateiname ist fns03912**  
**Eindeutiger Dateiname ist fnt03912**  
**Eindeutiger Dateiname ist fnu03912**  
**Eindeutiger Dateiname ist fnv03912**  
**Eindeutiger Dateiname ist fnw03912**  
**Eindeutiger Dateiname ist fnx03912**  
**Eindeutiger Dateiname ist fny03912**  
**Eindeutiger Dateiname ist fnz03912**  
**Problem, das die Vorlage erstellt.**  
**Aus eindeutigen Dateinamen heraus.**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_getpid](../../c-runtime-library/reference/getpid.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)