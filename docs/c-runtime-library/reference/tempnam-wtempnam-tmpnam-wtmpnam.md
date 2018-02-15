---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wtempnam
- _wtmpnam
- wtmpnam
- tmpnam
- _wtempnam
- _tempnam
dev_langs:
- C++
helpviewer_keywords:
- wtempnam function
- file names [C++], creating temporary
- _tempnam function
- ttmpnam function
- tmpnam function
- tempnam function
- wtmpnam function
- temporary files, creating
- file names [C++], temporary
- _ttmpnam function
- _wtmpnam function
- _wtempnam function
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29b0f7f645bd23c04e9d9f31dc914e29f7a048cb
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="tempnam-wtempnam-tmpnam-wtmpnam"></a>_tempnam, _wtempnam, tmpnam, _wtmpnam
Generiert Namen, die Sie verwenden können, um temporäre Dateien zu erstellen. Sicherere Versionen einiger dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [tmpnam_s, _wtmpnam_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md).  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `prefix`  
 Die Zeichenfolge, die den von `_tempnam` zurückgegebenen Namen vorangestellt wird.  
  
 `dir`  
 Der im Dateinamen verwendete Pfad, wenn es keine TMP-Umgebungsvariable gibt oder wenn TMP kein gültiges Verzeichnis ist.  
  
 `str`  
 Zeiger, der den generierten Namen enthält und mit dem von der Funktion zurückgegebenen Namen identisch ist. Dies ist eine einfache Möglichkeit, den generierten Namen zu speichern.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede Funktion gibt einen Zeiger auf den erzeugten Namen zurück oder `NULL`, falls ein Fehler vorliegt. Fehler kann auftreten, wenn Sie versuchen, mehr als `TMP_MAX` (Siehe STDIO. H) Aufrufe mit `tmpnam` oder bei Verwendung von `_tempnam` und es ist ein Ungültiger Verzeichnisname angegeben, in der TMP-Umgebungsvariable und die `dir` Parameter.  
  
> [!NOTE]
>  Die von `tmpnam` und `_wtmpnam` zurückgegebenen Zeiger zeigen auf die internen statischen Puffer. [free](../../c-runtime-library/reference/free.md) sollte nicht aufgerufen werden, um die Zuordnung dieser Zeiger aufzuheben. `free` muss für von `_tempnam` und `_wtempnam` zugeordnete Zeiger aufgerufen werden.  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen gibt den Namen einer Datei zurück, die derzeit nicht vorhanden ist. `tmpnam` gibt einen Namen in das aktuelle Arbeitsverzeichnis ein, und `_tempnam` ermöglicht Ihnen, einen eindeutigen Namen in einem anderen Verzeichnis als dem aktuellen zu generieren. Wenn einem Dateinamen ohne Pfadinformationen ein umgekehrter Schrägstrich vorangestellt ist, wie z.B. \fname21, weist dies darauf hin, dass der Name für das aktuelle Arbeitsverzeichnis gültig ist.  
  
 Für `tmpnam` können Sie diesen generierten Dateinamen in `str` speichern. Wenn `str` `NULL` ist, dann hinterlässt `tmpnam` das Ergebnis in einem internen statischen Puffer. Alle nachfolgenden Aufrufe zerstören deshalb diesen Wert. Der von `tmpnam` generierte Name besteht aus einem vom Programm generierten Dateinamen und nach dem ersten Aufruf von `tmpnam` aus einer Dateierweiterung aus aufeinanderfolgenden Zahlen mit Basis 32 (.1-.vvu, wenn `TMP_MAX` in STDIO.H 32,767 ist).  
  
 `_tempnam` generiert einen eindeutigen Dateinamen für ein Verzeichnis, das durch die folgenden Regeln ausgewählt wird:  
  
-   Wenn die TMP-Umgebungsvariable definiert und auf einen gültigen Verzeichnisnamen festgelegt ist, werden eindeutige Dateinamen für das von TMP angegebene Verzeichnis generiert.  
  
-   Wenn die TMP-Umgebungsvariable nicht definiert oder wenn sie auf den Namen eines nicht vorhandenen Verzeichnisses festgelegt ist, verwendet `_tempnam` den `dir`-Parameter als Pfad, für den eindeutige Namen generiert werden.  
  
-   Wenn die TMP-Umgebungsvariable nicht definiert oder wenn sie auf den Namen eines nicht vorhandenen Verzeichnisses festgelegt ist, und wenn `dir` entweder `NULL` oder auf den Namen eines nicht vorhandenen Verzeichnisses festgelegt ist, verwendet `_tempnam` das aktuelle Arbeitsverzeichnis, um eindeutige Namen zu generieren. Wenn TMP und `dir` Namen von Verzeichnissen angeben, die nicht vorhanden sind, schlägt die `_tempnam`-Funktion zurzeit fehl.  
  
 Der von `_tempnam` zurückgegebene Name ist eine Verkettung von `prefix` und einer sequentiellen Nummer, die kombiniert werden, um einen eindeutigen Verzeichnisnamen für das angegebene Verzeichnis zu erstellen. `_tempnam` generiert Dateinamen, die keine Erweiterung haben. `_tempnam` verwendet [malloc](../../c-runtime-library/reference/malloc.md), um Arbeitsspeicher für den Dateinamen zuzuweisen. Das Programm ist für die Freigabe dieses Speicherplatzes verantwortlich, wenn er nicht mehr benötigt wird.  
  
 `_tempnam` und `tmpnam` behandeln Multibyte-Zeichenfolgenargumente automatisch als richtig. Die Erkennung von Multibyte-Zeichenfolgen erfolgt auf der Grundlage der Codepage des OEM aus dem Betriebssystem. `_wtempnam` ist eine Breitzeichenversion von `_tempnam`. Die Argumente und der Rückgabewert von `_wtempnam` sind Zeichenfolgen mit Breitzeichen. `_wtempnam` und `_tempnam` verhalten sich nahezu identisch, allerdings verarbeitet `_wtempnam` keine Multibyte-Zeichenfolgen. `_wtmpnam` ist eine Breitzeichenversion von `tmpnam`. Das Argument und der Rückgabewert von `_wtmpnam` sind Zeichenfolgen mit Breitzeichen. `_wtmpnam` und `tmpnam` verhalten sich nahezu identisch, allerdings verarbeitet `_wtmpnam` keine Multibyte-Zeichenfolgen.  
  
 Wenn `_DEBUG` und `_CRTDBG_MAP_ALLOC` definiert sind, werden `_tempnam` und `_wtempnam` durch Aufrufe für [_tempnam_dbg und _wtempnam_dbg](../../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md) ersetzt.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttmpnam`|`tmpnam`|`tmpnam`|`_wtmpnam`|  
|`_ttempnam`|`_tempnam`|`_tempnam`|`_wtempnam`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_tempnam`|\<stdio.h>|  
|`_wtempnam`, `_wtmpnam`|\<stdio.h> oder \<wchar.h>|  
|`tmpnam`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
\s1gk. is safe to use as a temporary file.  
C:\DOCUME~1\user\LOCALS~1\Temp\2\stq2 is safe to use as a temporary file.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)