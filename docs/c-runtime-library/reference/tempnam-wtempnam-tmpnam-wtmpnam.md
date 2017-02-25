---
title: "_tempnam, _wtempnam, tmpnam, _wtmpnam | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wtempnam"
  - "_wtmpnam"
  - "tmpnam"
  - "_tempnam"
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
  - "wtempnam"
  - "_wtmpnam"
  - "wtmpnam"
  - "tmpnam"
  - "_wtempnam"
  - "_tempnam"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tempnam-Funktion"
  - "_ttmpnam-Funktion"
  - "_wtempnam-Funktion"
  - "_wtmpnam-Funktion"
  - "Dateinamen [C++], Erstellen temporärer"
  - "Dateinamen [C++], Temporär"
  - "tempnam-Funktion"
  - "Temporäre Dateien, Erstellen"
  - "tmpnam-Funktion"
  - "ttmpnam-Funktion"
  - "wtempnam-Funktion"
  - "wtmpnam-Funktion"
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _tempnam, _wtempnam, tmpnam, _wtmpnam
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generieren Sie Namen, die Sie verwenden können, um temporäre Dateien zu erstellen.  Sicherere Versionen einiger dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [tmpnam\_s, \_wtmpnam\_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md).  
  
## Syntax  
  
```  
char *_tempnam(  
   const char *dir,  
   const char *prefix   
);  
wchar_t *_wtempnam(  
   const wchar_t *dir,  
   const wchar_t *prefix   
);  
char *tmpnam(  
   char *str   
);  
wchar_t *_wtmpnam(  
   wchar_t *str   
);  
```  
  
#### Parameter  
 `prefix`  
 Die Zeichenfolge, die den Namen vorangestellt wird, der von `_tempnam` zurück.  
  
 `dir`  
 Der Pfad verwendet im Dateinamen, wenn keine TMP\-Umgebungsvariable vorhanden ist oder wenn TMP kein gültiges Verzeichnis befindet.  
  
 `str`  
 Zeiger, der den generierten Namen enthält und dem Namen identisch ist, der von der Funktion zurückgegeben.  Dies ist eine einfache Möglichkeit, den generierten Namen zu speichern.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger an das generierte Namen oder `NULL` zurück, wenn ein Fehler auftritt.  Fehler kann, wenn Sie versuchen, mehr als `TMP_MAX` vorkommen \(siehe STDIO.H\) Aufrufe mit `tmpnam` oder wenn Sie `_tempnam` verwenden und es ist ein ungültiger Verzeichnisname, der i TMP\-Umgebungsvariable und im `dir`\-Parameter angegeben.  
  
> [!NOTE]
>  Die Zeiger, die von `tmpnam` und `_wtmpnam` zurückgegeben werden, zeigen auf statischen internen Puffer.  [frei](../../c-runtime-library/reference/free.md) sollte nicht aufgerufen werden, um diesen Zeiger freizugeben.  `free` muss für Zeiger die aufgerufen werden, die von `_tempnam` und `_wtempnam` zugeordnet sind.  
  
## Hinweise  
 Jede dieser Funktionen gibt den Namen einer Datei zurück, die nicht vorhanden ist.  `tmpnam` gibt einen Namen ab, der im aktuellen Arbeitsverzeichnis eindeutig ist und `_tempnam` können Sie einen eindeutigen Namen in einem Verzeichnis als die aktuelle generieren.  Hinweis, als wenn ein Dateiname mit einem umgekehrten Schrägstrich und keine Pfadinformationen, beispielsweise \\fname21, diese vorangestellt wird, gibt an, dass der Name für das aktuelle Arbeitsverzeichnis gültig ist.  
  
 Für `tmpnam` können Sie diesen erzeugten Dateinamen im `str` speichern.  Wenn `str``NULL` ist, dann bleibt `tmpnam` das Ergebnis in einem internen statischen Puffer.  So zerstören alle nachfolgenden Aufrufe diesen Wert.  Der Name, der von `tmpnam` generiert wurde, besteht aus einem Programm\-generierten Dateinamen, und nach dem ersten Aufruf von `tmpnam` aus, eine Dateierweiterung von sequenziellen Zahlen in Basis 32 \(.1\-.vvu, wenn `TMP_MAX` in STDIO.H 32.767 ist\).  
  
 `_tempnam` generiert einen eindeutigen Dateinamen für ein Verzeichnis, das durch die folgenden Regeln ausgewählt wird:  
  
-   Wenn die TMP\-Umgebungsvariable auf einen gültigen Verzeichnisnamen definiert und festgelegt wird, sind eindeutige Dateinamen für das Verzeichnis generiert, das von TMP angegeben wird.  
  
-   Wenn die TMP\-Umgebungsvariable nicht definiert wird, oder, wenn diese auf den Namen eines Verzeichnisses festgelegt wird, das nicht vorhanden ist, verwendet `_tempnam` den `dir`\-Parameter als Pfad, für den er eindeutige Namen generiert.  
  
-   Wenn die TMP\-Umgebungsvariable nicht definiert wird, oder, wenn er auf den Namen eines Verzeichnisses festgelegt wird, das nicht vorhanden ist, und wenn `dir` entweder `NULL` oder mehreren in den Namen eines Verzeichnisses, das nicht vorhanden ist, verwendet `_tempnam` das aktuelle Arbeitsverzeichnis, um eindeutige Namen zu generieren.  Derzeit wenn TMP und `dir` Namen von Verzeichnissen angeben, die nicht vorhanden sind, generiert der Funktionsaufruf `_tempnam` aus.  
  
 Der Name, der von `_tempnam` zurückgegeben wird, ist eine Verkettung von `prefix` und von sequenziellen Zahl, die kombiniert, um einen eindeutigen Dateinamen für das angegebene Verzeichnis zu erstellen.  `_tempnam` generiert Dateinamen, die ohne Erweiterung geöffnet.  `_tempnam` verwendet [malloc](../../c-runtime-library/reference/malloc.md), um Platz für den Dateinamen zuzuordnen; das Programm ist für die Freigabe dieses Speichers zuständig, wenn es nicht mehr benötigt wird.  
  
 `_tempnam` und `tmpnam` verarbeiten automatisch Mehrbyte\-Zeichenfolgen\-Argumente entsprechend und erkennen Mehrbytezeichensequenzen entsprechend der OEM\-Codepage, die vom Betriebssystem abgerufen wird.  `_wtempnam` ist eine Breitzeichen\-Version von `_tempnam`; die Argumente und der Rückgabewert von `_wtempnam` sind Zeichenfolgen mit Breitzeichen.  `_wtempnam` und `_tempnam` identisch verhalten sich, dass `_wtempnam` nicht behandelt Mehrbyte\-Zeichenfolgen.  `_wtmpnam` ist eine Breitzeichenversion von `tmpnam`. Das Argument und der Rückgabewert von `_wtmpnam` sind Zeichenfolgen mit Breitzeichen.  `_wtmpnam` und `tmpnam` identisch verhalten sich, dass `_wtmpnam` nicht behandelt Mehrbyte\-Zeichenfolgen.  
  
 Wenn `_DEBUG` und `_CRTDBG_MAP_ALLOC` definiert werden, sind `_tempnam` und `_wtempnam` durch Aufrufe [\_tempnam\_dbg und \_wtempnam\_dbg](../../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md) ersetzt.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_ttmpnam`|`tmpnam`|`tmpnam`|`_wtmpnam`|  
|`_ttempnam`|`_tempnam`|`_tempnam`|`_wtempnam`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_tempnam`|\<stdio.h\>|  
|`_wtempnam`, `_wtmpnam`|\<stdio.h\> oder \<wchar.h\>|  
|`tmpnam`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_tempnam.c  
// compile with: /W3  
// This program uses tmpnam to create a unique filename in the  
// current working directory, then uses _tempnam to create   
// a unique filename with a prefix of stq.   
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char* name1 = NULL;  
   char* name2 = NULL;  
  
   // Create a temporary filename for the current working directory:   
   if( ( name1 = tmpnam( NULL ) ) != NULL ) // C4996  
   // Note: tmpnam is deprecated; consider using tmpnam_s instead  
      printf( "%s is safe to use as a temporary file.\n", name1 );  
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // Create a temporary filename in temporary directory with the  
   // prefix "stq". The actual destination directory may vary  
   // depending on the state of the TMP environment variable and  
   // the global variable P_tmpdir.     
  
   if( ( name2 = _tempnam( "c:\\tmp", "stq" ) ) != NULL )  
      printf( "%s is safe to use as a temporary file.\n", name2 );   
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // When name2 is no longer needed :     
   if(name2)  
     free(name2);  
  
}  
```  
  
  **\\ s1gk. ist sicher, als temporäre Datei zu verwenden.**  
**C:\\DOCUME~1\\user\\LOCALS~1\\Temp\\2\\stq2 ist sicher, als temporäre Datei zu verwenden.**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md)