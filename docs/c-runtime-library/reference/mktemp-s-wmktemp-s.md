---
title: "_mktemp_s, _wmktemp_s"
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
  - "_mktemp_s"
  - "_wmktemp_s"
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
  - "wmktemp_s"
  - "mktemp_s"
  - "_mktemp_s"
  - "_wmktemp_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mktemp_s-Funktion"
  - "_tmktemp_s-Funktion"
  - "_wmktemp_s-Funktion"
  - "Dateien [C++], Temporär"
  - "mktemp_s-Funktion"
  - "Temporäre Dateien [C++]"
  - "tmktemp_s-Funktion"
  - "wmktemp_s-Funktion"
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
caps.latest.revision: 23
caps.handback.revision: "23"
ms.author: "corob"
manager: "ghogen"
---
# _mktemp_s, _wmktemp_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt einen eindeutigen Dateinamen.  Diese Versionen von [\_mktemp, \_wmktemp](../../c-runtime-library/reference/mktemp-wmktemp.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _mktemp_s(  
   char *template,  
   size_t sizeInChars  
);  
errno_t _wmktemp_s(  
   wchar_t *template,  
   size_t sizeInChars  
);  
template <size_t size>  
errno_t _mktemp_s(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
errno_t _wmktemp_s(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### Parameter  
 `template`  
 Dateinamenmuster.  
  
 `sizeInChars`  
 Größe des Puffers in den Einzelbytezeichen in `_mktemp_s`; Breitzeichen in `_wmktemp_s`, einschließlich das NULL\-Zeichen.  
  
## Rückgabewert  
 NULL zurückgeben beider Funktionen bei Erfolg; ein Fehlercode auf Fehler.  
  
### Fehlerbedingungen  
  
|`template`|`sizeInChars`|**Rückgabewert**|**neuen Wert in der Vorlage**|  
|----------------|-------------------|----------------------|-----------------------------------|  
|`NULL`|any|`EINVAL`|`NULL`|  
|Falsches Format \(siehe `Remarks`\-Abschnitt zur ordnungsgemäßen Format\)|any|`EINVAL`|leere Zeichenfolge|  
|any|\<\= Zahl von X|`EINVAL`|leere Zeichenfolge|  
  
 Wenn eine der oben genannten Fehlerzustände, tritt der ungültige Parameterhandler wird aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, wird `errno` auf `EINVAL` festgelegt und die Funktionen gibt `EINVAL` zurück.  
  
## Hinweise  
 Die Funktion `_mktemp_s` erstellt einen eindeutigen Dateinamen, indem das Argument `template`, sodass ändert, nachdem der Aufruf, der `template` Zeiger auf eine Zeichenfolge zeigt, die den neuen Dateinamen enthält.  `_mktemp_s` behandelt automatisch Mehrbyte\-Zeichenfolgen\-Argumente entsprechend und derzeit erkennt Mehrbytezeichensequenzen entsprechend der Mehrbyte\-Codepage vom Laufzeitsystem.  `_wmktemp_s` ist eine Breitzeichen\-Version von `_mktemp_s`; das Argument von `_wmktemp_s` ist eine Zeichenfolge mit Breitzeichen.  `_wmktemp_s` und `_mktemp_s` identisch verhalten sich andernfalls, dass `_wmktemp_s` nicht behandelt Mehrbyte\-Zeichenfolgen.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tmktemp_s`|`_mktemp_s`|`_mktemp_s`|`_wmktemp_s`|  
  
 Das Argument `template` hat die Form `baseXXXXXX`, wobei `base` der Teil des neuen Dateinamen ist, den Sie bereitstellen und jedes X ist ein Platzhalter für ein Zeichen, das von `_mktemp_s` angegeben wird.  Jedes Platzhalterzeichen in `template` muss einem Großbuchstaben X. sein.  `_mktemp_s` verwaltet `base` bei und ersetzt das erste schleppende X durch ein alphabetisches Zeichen.  `_mktemp_s` ersetzt folgenden nachfolgenden Xs durch einen fünfstelligen Wert; Dieser Wert ist eine eindeutige Zahl, die den aufrufenden Prozesses oder in Multithreadprogrammen, der aufrufende Thread gekennzeichnet.  
  
 Jeder erfolgreichen Aufruf von `_mktemp_s` ändert `template`.  In jedem nachfolgenden Aufrufs vom selben Prozess oder der Thread mit demselben `template`\-Argument, `_mktemp_s` Überprüfungen für Dateinamen, dass Abgleichungsnamen durch `_mktemp_s` in vorherigen Aufrufen zurückkehrten.  Wenn keine Datei für einen angegebenen Namen vorhanden ist, die `_mktemp_s` zurückgibt, benennen.  Wenn Dateien für alle vorher zurückgegebenen Namen vorhanden, erstellt `_mktemp_s` einen neuen Namen, indem das alphabetisches Zeichen, das er im zuvor zurückgegebenen Namen mit dem nächsten verfügbaren Kleinbuchstaben verwendete, in der Reihenfolge, von "a" bis "z".  Wenn `base` ist:  
  
```  
fn  
```  
  
 und der fünfstellige Wert, der von `_mktemp_s` angegeben wird, ist der zurückgegebene 12345, Vorname ist:  
  
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
  
 `_mktemp_s` kann maximal 26 eindeutige Dateinamen für eine bestimmte Kombination von Basis\- und Vorlagenwerten erstellen.  Daher ist FNZ12345 der letzte eindeutige Dateiname `_mktemp_s` kann für `base` erstellen und `template` beschränkt wird in diesem Beispiel.  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mktemp_s`|\<io.h\>|  
|`_wmktemp_s`|\<io.h oder\> wchar.h \<\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_mktemp_s.cpp  
/* The program uses _mktemp to create  
 * five unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
  
char *fnTemplate = "fnXXXXXX";  
char names[5][9];  
  
int main()  
{  
   int i, err, sizeInChars;  
   FILE *fp;  
  
   for( i = 0; i < 5; i++ )  
   {  
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );  
      /* Get the size of the string and add one for the null terminator.*/  
      sizeInChars = strnlen(names[i], 9) + 1;  
      /* Attempt to find a unique filename: */  
      err = _mktemp_s( names[i], sizeInChars );  
      if( err != 0 )  
         printf( "Problem creating the template" );  
      else  
      {  
         if( fopen_s( &fp, names[i], "w" ) == 0 )  
            printf( "Unique filename is %s\n", names[i] );  
         else  
            printf( "Cannot open %s\n", names[i] );  
         fclose( fp );  
      }  
   }  
  
   return 0;  
}  
```  
  
## Beispielausgabe  
  
```  
Unique filename is fna03188  
Unique filename is fnb03188  
Unique filename is fnc03188  
Unique filename is fnd03188  
Unique filename is fne03188  
```  
  
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
 [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md)