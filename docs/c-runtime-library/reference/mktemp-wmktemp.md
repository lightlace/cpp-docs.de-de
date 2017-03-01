---
title: _mktemp, _wmktemp | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wmktemp
- _mktemp
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
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
dev_langs:
- C++
helpviewer_keywords:
- _wmktemp function
- _mktemp function
- files [C++], temporary
- tmktemp function
- _tmktemp function
- wmktemp function
- mktemp function
- temporary files [C++]
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: b6b5f2f059084e1f5dd66d75b5f5af5f2ade2473
ms.lasthandoff: 02/24/2017

---
# <a name="mktemp-wmktemp"></a>_mktemp, _wmktemp
Vergibt einen eindeutigen Dateinamen. Für diese Funktionen sind sicherere Versionen verfügbar. Informationen dazu finden Sie unter [_mktemp_s, _wmktemp_s](../../c-runtime-library/reference/mktemp-s-wmktemp-s.md).  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `template`  
 Muster des Dateinamens.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf die geänderte Vorlage zurück. Die Funktion gibt `NULL` zurück, wenn `template` nicht richtig aufgebaut ist oder aus der jeweiligen Vorlage keine weiteren eindeutigen Namen mehr vergeben werden können.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_mktemp` vergibt einen eindeutigen Dateinamen, indem das Argument `template` geändert wird. `_mktemp` behandelt Multibyte-Zeichenfolgenargumente automatisch richtig. Die Erkennung von Multibyte-Zeichenfolgen erfolgt auf Grundlage der vom Laufzeitsystem zum jeweiligen Zeitpunkt verwendeten Multibyte-Codeseite. `_wmktemp` ist eine Breitzeichenversion von `_mktemp`. Das Argument und der Rückgabewert von `_wmktemp` sind Zeichenfolgen mit Breitzeichen. `_wmktemp` und `_mktemp` verhalten sich ansonsten identisch. Allerdings verarbeitet `_wmktemp` keine Multibyte-Zeichenfolgen.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmktemp`|`_mktemp`|`_mktemp`|`_wmktemp`|  
  
 Das Argument `template` hat das Format `base`XXXXXX, wobei es sich bei `base` um den von Ihnen angegebenen Teil des neuen Dateinamens und bei den einzelnen X um Platzhalter für ein von `_mktemp` bereitgestelltes Zeichen handelt. Die einzelnen Platzhalterzeichen in `template` müssen als X in Großschreibung angegeben sein. `_mktemp` behält `base` bei und ersetzt das erste nachgestellte X mit einem alphabetischen Zeichen. `_mktemp` ersetzt das nächste nachgestellte X mit einem fünfstelligen Wert. Bei diesem Wert handelt es sich um eine eindeutige Nummer, die zur Identifizierung des aufrufenden Prozesses bzw. in Multithreadprogrammen des aufrufenden Threads dient.  
  
 Bei jedem erfolgreichen Aufruf von `_mktemp` wird `template` geändert. Bei jedem darauffolgenden Aufruf aus demselben Prozess oder Thread mit demselben Argument `template` sucht `_mktemp` nach Dateinamen, die den von `_mktemp` im Rahmen vorheriger Aufrufe zurückgegebenen Namen entsprechen. Wenn für einen bestimmten Namen keine Datei vorhanden ist, gibt `_mktemp` diesen Namen zurück. Wenn für alle zuvor zurückgegebenen Namen Dateien vorhanden sind, erstellt `_mktemp` einen neuen Namen, indem das im zuvor zurückgegebenen Namen enthaltene alphabetische Zeichen durch den nächsten verfügbaren Kleinbuchstaben (in absteigender Reihenfolge von „a“ bis „z“) ersetzt wird. Ist `base` beispielsweise  
  
```  
fn  
```  
  
 und der von `_mktemp` bereitgestellte fünfstellige Wert 12345, lautet der erste zurückgegebene Name:  
  
```  
fna12345  
```  
  
 Wenn dieser Name verwendet wird, um die Datei FNA12345 zu erstellen, und diese Datei noch vorhanden ist, lautet der nächste bei einem Aufruf aus demselben Prozess oder Thread mit demselben `base` für `template` zurückgegebene Name:  
  
```  
fnb12345  
```  
  
 Ist FNA12345 nicht vorhanden, lautet der nächste zurückgegebene Name erneut:  
  
```  
fna12345  
```  
  
 `_mktemp` kann bis zu 26 eindeutige Dateinamen für eine beliebige Kombination aus Basis- und Vorlagenwerten erstellen. Daher ist FNZ12345 der letzte eindeutige Dateiname, den `_mktemp` für die in diesem Beispiel verwendeten Werte für `base` und `template` vergeben kann.  
  
 Bei Fehlern wird `errno` festgelegt. Handelt es sich bei `template` um ein ungültiges Format, (z.B. weniger als sechs X), wird für `errno` `EINVAL` festgelegt. Wenn `_mktemp` keinen eindeutigen Namen vergeben kann, da alle 26 möglichen Dateinamen bereits vorhanden sind, legt `_mktemp` für die Vorlage eine leere Zeichenfolge fest und gibt `EEXIST` zurück.  
  
 In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_mktemp`|\<io.h>|  
|`_wmktemp`|\<io.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
Unique filename is fna03912  
Unique filename is fnb03912  
Unique filename is fnc03912  
Unique filename is fnd03912  
Unique filename is fne03912  
Unique filename is fnf03912  
Unique filename is fng03912  
Unique filename is fnh03912  
Unique filename is fni03912  
Unique filename is fnj03912  
Unique filename is fnk03912  
Unique filename is fnl03912  
Unique filename is fnm03912  
Unique filename is fnn03912  
Unique filename is fno03912  
Unique filename is fnp03912  
Unique filename is fnq03912  
Unique filename is fnr03912  
Unique filename is fns03912  
Unique filename is fnt03912  
Unique filename is fnu03912  
Unique filename is fnv03912  
Unique filename is fnw03912  
Unique filename is fnx03912  
Unique filename is fny03912  
Unique filename is fnz03912  
Problem creating the template.  
Out of unique filenames.  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_getpid](../../c-runtime-library/reference/getpid.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)
