---
title: _searchenv_s, _wsearchenv_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsearchenv_s
- _searchenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
dev_langs: C++
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
caps.latest.revision: "32"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8d2b78a892308b6984ef11d317cf46c1d46ca6ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="searchenvs-wsearchenvs"></a>_searchenv_s, _wsearchenv_s
Sucht mithilfe von Umgebungspfaden nach einer Datei. Diese Versionen von [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char *pathname,  
   size_t numberOfElements  
);  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `filename`  
 Der Name der zu suchenden Datei.  
  
 [in] `varname`  
 Zu durchsuchende Umgebung.  
  
 [out] `pathname`  
 Puffer zum Speichern des vollständigen Pfades.  
  
 [in] `numberOfElements`  
 Größe der `pathname` Puffer.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.  
  
 Wenn `filename` eine leere Zeichenfolge ist, dann ist der Rückgabewert `ENOENT`.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`filename`|`varname`|`pathname`|`numberOfElements`|Rückgabewert|Inhalt von `pathname`|  
|----------------|---------------|----------------|------------------------|------------------|----------------------------|  
|any|alle|`NULL`|any|`EINVAL`|nicht verfügbar|  
|`NULL`|alle|alle|alle|`EINVAL`|nicht geändert|  
|any|alle|any|<= 0|`EINVAL`|nicht geändert|  
  
 Wenn eine dieser Fehlerbedingungen auftritt, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_searchenv_s`-Routine sucht in der angegebenen Domäne nach der Zieldatei. Die `varname`-Variable kann jede beliebige Umgebungsvariable oder benutzerdefinierte Variable sein, die eine Liste von Verzeichnispfaden angibt, wie z. B. `PATH`, `LIB` und `INCLUDE`. Da `_searchenv_s` die Groß-/Kleinschreibung beachtet, sollte `varname` mit der Groß-/Kleinschreibung der Umgebungsvariablen übereinstimmen. Wenn `varname` nicht mit dem Namen einer in der Umgebung des Prozesses definierten Umgebungsvariablen übereinstimmt, gibt die Funktion Null zurück und die Variable `pathname` bleibt unverändert.  
  
 Die Routine sucht zuerst im aktuellen Arbeitsverzeichnis nach der Datei. Wenn die Datei dort nicht gefunden wird, werden als Nächstes die in der Umgebungsvariablen angegebenen Verzeichnisse durchsucht. Wenn die Zieldatei in einem dieser Verzeichnisse ist, wird der neu erstellte Pfad in `pathname` kopiert. Wenn die Datei `filename` nicht gefunden wird, enthält `pathname` eine leere auf NULL abschließende Zeichenfolge.  
  
 Der Puffer `pathname` sollte mindestens `_MAX_PATH` Zeichen lang sein, um die volle Länge des erstellten Pfadnamens zu unterstützen. Andernfalls kann `_searchenv_s` den `pathname`-Puffer überlaufen lassen, was zu einem unerwarteten Verhalten führt.  
  
 `_wsearchenv_s` ist eine Breitzeichenversion von `_searchenv_s`. Die Argumente für `_wsearchenv_s` sind Zeichenfolgen mit Breitzeichen. `_wsearchenv_s` und `_searchenv_s` verhalten sich andernfalls identisch.  
  
 In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsearchenv_s`|`_searchenv_s`|`_searchenv_s`|`_wsearchenv_s`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_searchenv_s`|\<stdlib.h>|  
|`_wsearchenv_s`|\<stdlib.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_searchenv_s.c  
/* This program searches for a file in  
 * a directory specified by an environment variable.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
   errno_t err;  
  
   /* Search for file in PATH environment variable: */  
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );  
   if (err != 0)  
   {  
      printf("Error searching the path. Error code: %d\n", err);  
   }  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
```Output  
Path for CL.EXE:  
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)   
 [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)