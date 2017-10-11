---
title: rename, _wrename | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- rename
- _wrename
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
- _wrename
- _trename
- Rename
dev_langs:
- C++
helpviewer_keywords:
- trename function
- directories [C++], renaming
- renaming directories
- names [C++], changing file
- _trename function
- rename function
- wrename function
- files [C++], renaming
- _wrename function
- names [C++], changing directory
- renaming files
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 5324b594631f0d45a49d04e771318a84d101fc32
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="rename-wrename"></a>rename, _wrename
Benennt eine Datei oder ein Verzeichnis um.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int rename(  
   const char *oldname,  
   const char *newname   
);  
int _wrename(  
   const wchar_t *oldname,  
   const wchar_t *newname   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *oldname*  
 Zeiger auf den alten Namen.  
  
 *newname*  
 Zeiger auf den neuen Namen.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt bei Erfolg 0 zurück. Bei einem Fehler gibt die Funktion einen Wert ungleich null zurück und legt `errno` auf einen der folgenden Werte fest:  
  
 `EACCES`  
 Die Datei oder das Verzeichnis, das von *newname* angegeben wird, ist bereits vorhanden oder konnte nicht erstellt werden (ungültiger Pfad). Möglicherweise ist auch *oldname* ein Verzeichnis, und *newname* gibt einen anderen Pfad an.  
  
 `ENOENT`  
 Von *oldname* angegebene Datei oder Pfad wurden nicht gefunden.  
  
 `EINVAL`  
 Name enthält ungültige Zeichen.  
  
 Weitere mögliche Rückgabewerte finden Sie unter [_doserrno, _errno, syserrlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die **rename**-Funktion benennt die Datei oder das Verzeichnis, die von *oldname* angegeben wurden, auf den von *newname* gegebenen Namen. Der alte Name muss der Pfad einer vorhandenen Datei oder eines vorhandenen Verzeichnisses sein. Der neue Name darf nicht der Name einer vorhandenen Datei oder eines vorhandenen Verzeichnisses sein. Sie können **rename** nutzen, um eine Datei von einem Verzeichnis oder Gerät zu einem anderen zu verschieben, indem Sie einen anderen Pfad im *newname*-Argument angeben. Allerdings können Sie **rename** nicht verwenden, um ein Verzeichnis zu verschieben. Verzeichnisse können umbenannt, aber nicht verschoben werden.  
  
 `_wrename` ist eine Breitzeichenversion von **_rename**. Die Argumente für `_wrename` sind Breitzeichenfolgen. `_wrename` und **_rename** verhalten sich andernfalls identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_trename`|**rename**|**rename**|`_wrename`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|**rename**|\<io.h> oder \<stdio.h>|  
|`_wrename`|\<stdio.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_renamer.c  
/* This program attempts to rename a file named  
 * CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation  
 * to succeed, a file named CRT_RENAMER.OBJ must exist and  
 * a file named CRT_RENAMER.JBO must not exist.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int  result;  
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";  
  
   /* Attempt to rename file: */  
   result = rename( old, new );  
   if( result != 0 )  
      printf( "Could not rename '%s'\n", old );  
   else  
      printf( "File '%s' renamed to '%s'\n", old, new );  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)
