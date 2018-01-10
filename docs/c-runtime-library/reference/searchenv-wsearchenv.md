---
title: _searchenv, _wsearchenv | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _searchenv
- _wsearchenv
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
- _wsearchenv
- _tsearchenv
- wsearchenv
- _searchenv
- searchenv
dev_langs: C++
helpviewer_keywords:
- _wsearchenv function
- files [C++], finding
- _searchenv function
- tsearchenv function
- environment paths, searching for files
- _tsearchenv function
- wsearchenv function
- searchenv function
- environment paths
ms.assetid: 9c944a27-d326-409b-aee6-410e8762d9d3
caps.latest.revision: "33"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9996c9aad085beaef46d2a3188503eba582602d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="searchenv-wsearchenv"></a>_searchenv, _wsearchenv
Verwendet Umgebungspfade für die Suche nach einer Datei. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_searchenv_s, _wsearchenv_s](../../c-runtime-library/reference/searchenv-s-wsearchenv-s.md).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char *pathname   
);  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname   
);  
template <size_t size>  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Der Name der zu suchenden Datei.  
  
 `varname`  
 Zu durchsuchende Umgebung.  
  
 `pathname`  
 Puffer zum Speichern des vollständigen Pfades.  
  
## <a name="remarks"></a>Hinweise  
 Die `_searchenv`-Routine sucht in der angegebenen Domäne nach der Zieldatei. Die `varname`-Variable kann jede beliebige Umgebungsvariable oder benutzerdefinierte Variable sein, die eine Liste von Verzeichnispfaden angibt, wie z. B. `PATH`, `LIB` und `INCLUDE`. Da `_searchenv` die Groß-/Kleinschreibung beachtet, sollte `varname` mit der Groß-/Kleinschreibung der Umgebungsvariablen übereinstimmen.  
  
 Die Routine sucht zuerst im aktuellen Arbeitsverzeichnis nach der Datei. Wenn die Datei dort nicht gefunden wird, werden die in der Umgebungsvariablen angegebenen Verzeichnisse durchsucht. Wenn die Zieldatei in einem dieser Verzeichnisse ist, wird der neu erstellte Pfad in `pathname` kopiert. Wenn die Datei `filename` nicht gefunden wird, enthält `pathname` eine leere auf NULL abschließende Zeichenfolge.  
  
 Der Puffer `pathname` sollte mindestens `_MAX_PATH` Zeichen lang sein, um die volle Länge des erstellten Pfadnamens zu unterstützen. Andernfalls kann `_searchenv` den `pathname`-Puffer überlaufen lassen, was zu einem unerwarteten Verhalten führt.  
  
 `_wsearchenv` ist eine Breitzeichenversion von `_searchenv`. Die Argumente für `_wsearchenv` sind Zeichenfolgen mit Breitzeichen. `_wsearchenv` und `_searchenv` verhalten sich andernfalls identisch.  
  
 Wenn `filename` eine leere Zeichenfolge ist, geben diese Funktionen `ENOENT` zurück.  
  
 Wenn `filename` oder `pathname` ein `NULL`-Zeiger ist, wird der Handler für ungültige Parameter wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL`fest.  
  
 Weitere Informationen über `errno` und andere Fehlercodes finden Sie unter [errno-Konstanten](../../c-runtime-library/errno-constants.md).  
  
 In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsearchenv`|`_searchenv`|`_searchenv`|`_wsearchenv`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_searchenv`|\<stdlib.h>|  
|`_wsearchenv`|\<stdlib.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```C  
// crt_searchenv.c  
// compile with: /W3  
// This program searches for a file in  
// a directory that's specified by an environment variable.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
  
   // Search for file in PATH environment variable:  
   _searchenv( searchfile, envvar, pathbuffer ); // C4996  
   // Note: _searchenv is deprecated; consider using _searchenv_s  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
```Output  
Path for CL.EXE:  
C:\Program Files\Microsoft Visual Studio 8\VC\BIN\CL.EXE  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Directory Control (Verzeichnissteuerung)](../../c-runtime-library/directory-control.md)   
 [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [_searchenv_s, _wsearchenv_s](../../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)