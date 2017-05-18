---
title: _access_s, waccess_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _access_s
- _waccess_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- waccess_s
- access_s
- _waccess_s
- _access_s
dev_langs:
- C++
helpviewer_keywords:
- access_s function
- taccess_s function
- _taccess_s function
- waccess_s function
- _access_s function
- _waccess_s function
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
caps.latest.revision: 28
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
ms.openlocfilehash: 051c2e6a6b0315e2ca4ab3192f28a370d969ec5b
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="accesss-waccesss"></a>_access_s, _waccess_s
Bestimmt die Lese-/Schreibberechtigungen einer Datei. Dies ist eine sicherere Version von [_access, _waccess](../../c-runtime-library/reference/access-waccess.md), wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _access_s(   
   const char *path,   
   int mode   
);  
errno_t _waccess_s(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `path`  
 Datei oder Verzeichnispfad.  
  
 `mode`  
 Berechtigungseinstellung.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede Funktion gibt 0 zurück, wenn sich die Datei im angegebenen Modus befindet. Die Funktion gibt einen Fehlercode zurück, wenn die angegebene Datei nicht vorhanden ist oder im angegebenen Modus nicht auf sie zugegriffen werden kann. In diesem Fall gibt die Funktion einen Fehlercode zurück und legt `errno` auf diesen Code fest.  
  
 `EACCES`  
 Zugriff verweigert. Aufgrund der Berechtigungen wird der Zugriff im angegebenen Modus verweigert.  
  
 `ENOENT`  
 Der Dateiname oder der Pfad wurde nicht gefunden.  
  
 `EINVAL`  
 Ungültiger Parameter.  
  
 Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `_access_s`-Funktion für eine Datei verwendet wird, bestimmt diese, ob die Datei existiert und im angegebenen `mode` darauf zugegriffen werden darf. Wenn die Funktion dagegen mit einem Verzeichnispfad verwendet wird, bestimmt `_access_s` lediglich, ob dieses Verzeichnis existiert. Ab [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] bieten alle Verzeichnisse Lese- und Schreibzugriff.  
  
|Moduswert|überprüft nur, ob die Datei|  
|----------------|---------------------|  
|00|existiert.|  
|02|Schreibberechtigung.|  
|04|Leseberechtigung.|  
|06|Lese- und Schreibberechtigung.|  
  
 Die Berechtigung zum Lesen oder Schreiben einer Datei garantiert nicht, dass diese Datei auch geöffnet werden kann. Wenn beispielsweise ein anderer Prozess auf die Datei zugreift, kann möglicherweise auch dann nicht darauf zugegriffen werden, wenn `_access_s` 0 zurückgibt.  
  
 `_waccess_s` ist eine Breitzeichenversion von `_access_s`, wo das `path`-Argument für `_waccess_s` eine Breitzeichenfolge ist. Andernfalls verhalten sich `_waccess_s` und `_access_s` identisch.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `path` `NULL` ist oder `mode` keinen gültigen Modus angibt, wird der Ereignishandler für ungültige Parameter aufgerufen wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_taccess_s`|`_access_s`|`_access_s`|`_waccess_s`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_access_s`|\<io.h>|\<errno.h>|  
|`_waccess_s`|\<wchar.h> oder \<io.h>|\<errno.h>|  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird `_access_s` verwendet, um die Datei crt_access_s.c auf Existenz und Schreibberechtigung zu prüfen.  
  
```  
// crt_access_s.c  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    errno_t err = 0;  
  
    // Check for existence.   
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )  
    {  
        printf_s( "File crt_access_s.c exists.\n" );  
  
        // Check for write permission.   
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )  
        {  
            printf_s( "File crt_access_s.c does have "  
                      "write permission.\n" );  
        }  
        else  
        {  
            printf_s( "File crt_access_s.c does not have "  
                      "write permission.\n" );  
        }  
    }  
    else  
    {  
        printf_s( "File crt_access_s.c does not exist.\n" );  
    }  
}  
```  
  
```Output  
File crt_access_s.c exists.  
File crt_access_s.c does not have write permission.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_stat, _wstat-Funktionen](../../c-runtime-library/reference/stat-functions.md)
