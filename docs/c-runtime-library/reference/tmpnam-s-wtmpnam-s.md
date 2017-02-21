---
title: "tmpnam_s, _wtmpnam_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "tmpnam_s"
  - "_wtmpnam_s"
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
  - "tmpnam_s"
  - "_wtmpnam_s"
  - "L_tmpnam_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wtmpnam_s-Funktion"
  - "Dateinamen [C++], Erstellen temporärer"
  - "Dateinamen [C++], Temporär"
  - "L_tmpnam_s-Funktion"
  - "Temporäre Dateien, Erstellen"
  - "tmpnam_s-Funktion"
  - "wtmpnam_s-Funktion"
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# tmpnam_s, _wtmpnam_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generieren Sie Namen, die Sie verwenden können, um temporäre Dateien zu erstellen.  Diese Versionen sind von [tmpnam und \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t tmpnam_s(  
   char * str,  
   size_t sizeInChars   
);  
errno_t _wtmpnam_s(  
   wchar_t *str,  
   size_t sizeInChars   
);  
template <size_t size>  
errno_t tmpnam_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wtmpnam_s(  
   wchar_t (&str)[size]  
); // C++ only  
```  
  
#### Parameter  
 \[out\] `str`  
 Zeiger, der den generierten Namen enthält.  
  
 \[in\] `sizeInChars`  
 Die Größe des Puffers in Zeichen.  
  
## Rückgabewert  
 Beide Funktionen geben 0 zurück, wenn erfolgreich oder eine Fehlernummer auf Fehler.  
  
### Fehlerbedingungen  
  
|||||  
|-|-|-|-|  
|`str`|`sizeInChars`|**Rückgabewert**|**Contents of**  `str`|  
|`NULL`|any|`EINVAL`|nicht geändert|  
|nicht `NULL` \(Punkte zum gültigen Arbeitsspeicher\)|zu kurz|`ERANGE`|nicht geändert|  
  
 Wenn `str` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
## Hinweise  
 Jede dieser Funktionen gibt den Namen einer Datei zurück, die nicht vorhanden ist.  `tmpnam_s` gibt einen Namen ab, der im aktuellen Arbeitsverzeichnis eindeutig ist.  Hinweis, als wenn ein Dateiname mit einem umgekehrten Schrägstrich und keine Pfadinformationen, beispielsweise \\fname21, diese vorangestellt wird, gibt an, dass der Name für das aktuelle Arbeitsverzeichnis gültig ist.  
  
 Für `tmpnam_s` können Sie diesen erzeugten Dateinamen im `str` speichern.  Die maximale Länge einer Zeichenfolge, die von `tmpnam_s` zurückgegeben wird, ist `L_tmpnam_s`, die in STDIO.H.  Wenn `str``NULL` ist, dann bleibt `tmpnam_s` das Ergebnis in einem internen statischen Puffer.  So zerstören alle nachfolgenden Aufrufe diesen Wert.  Der Name, der von `tmpnam_s` generiert wurde, besteht aus einem Programm\-generierten Dateinamen, und nach dem ersten Aufruf von `tmpnam_s` aus, eine Dateierweiterung von sequenziellen Zahlen in Basis 32 \(.1\-.1vvvvvu, wenn `TMP_MAX_S` in STDIO.H INT\_MAX ist\).  
  
 `tmpnam_s` behandelt automatisch Mehrbyte\-Zeichenfolgen\-Argumente entsprechend und erkennt Mehrbytezeichensequenzen entsprechend der OEM\-Codepage, die vom Betriebssystem abgerufen wird.  `_wtmpnam_s` ist eine Breitzeichenversion von `tmpnam_s`. Das Argument und der Rückgabewert von `_wtmpnam_s` sind Zeichenfolgen mit Breitzeichen.  `_wtmpnam_s` und `tmpnam_s` identisch verhalten sich, dass `_wtmpnam_s` nicht behandelt Mehrbyte\-Zeichenfolgen.  
  
 Die Verwendung dieser Funktionen in C\+\+ wird durch Überladungen \(als Vorlagen vorhanden\) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_ttmpnam_s`|`tmpnam_s`|`tmpnam_s`|`_wtmpnam_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`tmpnam_s`|\<stdio.h\>|  
|`_wtmpnam_s`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_tmpnam_s.c  
// This program uses tmpnam_s to create a unique filename in the  
// current working directory.   
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char name1[L_tmpnam_s];  
   errno_t err;  
   int i;  
  
   for (i = 0; i < 15; i++)  
   {  
      err = tmpnam_s( name1, L_tmpnam_s );  
      if (err)  
      {  
         printf("Error occurred creating unique filename.\n");  
         exit(1);  
      }  
      else  
      {  
         printf( "%s is safe to use as a temporary file.\n", name1 );  
      }  
   }    
}  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md)