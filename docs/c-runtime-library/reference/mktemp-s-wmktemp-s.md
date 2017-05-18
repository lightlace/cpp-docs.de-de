---
title: _mktemp_s, _wmktemp_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mktemp_s
- _wmktemp_s
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
apitype: DLLExport
f1_keywords:
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
dev_langs:
- C++
helpviewer_keywords:
- _tmktemp_s function
- mktemp_s function
- _wmktemp_s function
- _mktemp_s function
- files [C++], temporary
- tmktemp_s function
- wmktemp_s function
- temporary files [C++]
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 6231031dd0bbc5b455e3555731f711ee7de971e7
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="mktemps-wmktemps"></a>_mktemp_s, _wmktemp_s
Erstellt einen eindeutigen Dateinamen. Dabei handelt es sich um Versionen von [_mktemp, _wmktem](../../c-runtime-library/reference/mktemp-wmktemp.md) mit den unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschriebenen Erweiterungen.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `template`  
 Muster des Dateinamens.  
  
 `sizeInChars`  
 Größe des Puffers in `_mktemp_s` in Einzelbytezeichen; Breitzeichen in `_wmktemp_s`, einschließlich NULL-Terminator.  
  
## <a name="return-value"></a>Rückgabewert  
 Beide Funktionen geben bei Erfolg null und bei Fehlern einen Fehlercode zurück.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`template`|`sizeInChars`|**Rückgabewert**|**Neuer Wert in Vorlage**|  
|----------------|-------------------|----------------------|-------------------------------|  
|`NULL`|alle|`EINVAL`|`NULL`|  
|Ungültiges Format (für gültiges Format siehe Abschnitt `Remarks`)|alle|`EINVAL`|Leere Zeichenfolge|  
|any|<= Anzahl von X|`EINVAL`|Leere Zeichenfolge|  
  
 Wenn eine der genannten Fehlerbedingungen auftritt, wird ein Handler für ungültige Parameter aufgerufen (siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md)). Wird die weitere Ausführung zugelassen, wird `errno` auf `EINVAL` gesetzt, und die Funktionen geben `EINVAL` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_mktemp_s` vergibt einen eindeutigen Dateinamen, indem sie das Argument `template` ändert. Auf diese Weise verweist der Zeiger für `template` nach dem Aufruf auf eine Zeichenfolge mit dem neuen Dateinamen. `_mktemp_s` behandelt Multibyte-Zeichenfolgenargumente automatisch richtig. Die Erkennung von Multibyte-Zeichenfolgen erfolgt auf Grundlage der vom Laufzeitsystem zum jeweiligen Zeitpunkt verwendeten Multibyte-Codeseite. Bei `_wmktemp_s` handelt es sich um eine Breitzeichenversion von `_mktemp_s`. Das Argument von `_wmktemp_s` ist eine Breitzeichenfolge. `_wmktemp_s` und `_mktemp_s` verhalten sich ansonsten identisch. Allerdings verarbeitet `_wmktemp_s` keine Multibyte-Zeichenfolgen.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmktemp_s`|`_mktemp_s`|`_mktemp_s`|`_wmktemp_s`|  
  
 Das Argument `template` hat das Format `baseXXXXXX`, wobei es sich bei `base` um den von Ihnen angegebenen Teil des neuen Dateinamens und bei den einzelnen X um Platzhalter für ein von `_mktemp_s` bereitgestelltes Zeichen handelt. Die einzelnen Platzhalterzeichen in `template` müssen als X in Großschreibung angegeben sein. `_mktemp_s` behält `base` bei und ersetzt das erste nachgestellte X mit einem alphabetischen Zeichen. `_mktemp_s` ersetzt das nächste nachgestellte X mit einem fünfstelligen Wert. Bei diesem Wert handelt es sich um eine eindeutige Nummer, die zur Identifizierung des aufrufenden Prozesses bzw. in Multithreadprogrammen des aufrufenden Threads dient.  
  
 Bei jedem erfolgreichen Aufruf von `_mktemp_s` wird `template` geändert. Bei jedem darauffolgenden Aufruf aus demselben Prozess oder Thread mit demselben Argument `template` sucht `_mktemp_s` nach Dateinamen, die den von `_mktemp_s` im Rahmen vorheriger Aufrufe zurückgegebenen Namen entsprechen. Wenn für einen bestimmten Namen keine Datei vorhanden ist, gibt `_mktemp_s` diesen Namen zurück. Wenn für alle zuvor zurückgegebenen Namen Dateien vorhanden sind, erstellt `_mktemp_s` einen neuen Namen, indem das im zuvor zurückgegebenen Namen enthaltene alphabetische Zeichen durch den nächsten verfügbaren Kleinbuchstaben (in absteigender Reihenfolge von „a“ bis „z“) ersetzt wird. Ist `base` beispielsweise  
  
```  
fn  
```  
  
 und der von `_mktemp_s` bereitgestellte fünfstellige Wert 12345, lautet der erste zurückgegebene Name:  
  
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
  
 `_mktemp_s` kann bis zu 26 eindeutige Dateinamen für eine beliebige Kombination aus Basis- und Vorlagenwerten erstellen. Daher ist FNZ12345 der letzte eindeutige Dateiname, den `_mktemp_s` für die in diesem Beispiel verwendeten Werte für `base` und `template` vergeben kann.  
  
 In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_mktemp_s`|\<io.h>|  
|`_wmktemp_s`|\<io.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
Unique filename is fna03188  
Unique filename is fnb03188  
Unique filename is fnc03188  
Unique filename is fnd03188  
Unique filename is fne03188  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_getpid](../../c-runtime-library/reference/getpid.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)
