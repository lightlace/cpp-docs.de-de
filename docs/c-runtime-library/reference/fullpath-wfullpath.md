---
title: _fullpath, _wfullpath | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fullpath
- _wfullpath
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
- wfullpath
- fullpath
- _wfullpath
- _fullpath
dev_langs:
- C++
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
caps.latest.revision: 18
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 7641c3cdc2a437d2c65f964ca6b1220992d11bca
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="fullpath-wfullpath"></a>_fullpath, _wfullpath
Erstellt einen absoluten oder vollständigen Pfadnamen für den angegebenen relativen Pfadnamen  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_fullpath(   
   char *absPath,  
   const char *relPath,  
   size_t maxLength   
);  
wchar_t *_wfullpath(   
   wchar_t *absPath,  
   const wchar_t *relPath,  
   size_t maxLength   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `absPath`  
 Zeiger auf einen Puffer, der den absoluten oder vollständigen Pfadnamen oder NULL enthält  
  
 `relPath`  
 Relativer Pfadname.  
  
 `maxLength`  
 Maximale Länge des Puffers des absoluten Pfadnamens (`absPath`). Die Länge wird für `_fullpath` in Bytes ausgedrückt, aber für `wchar_t` in Breitzeichen (`_wfullpath`).  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf einen Puffer zurück, der den absoluten Pfadnamen (`absPath`) enthält. Wenn ein Fehler auftritt (z.B, wenn der in `relPath` übergebene Wert einen Laufwerksbuchstaben enthält, der nicht gültig ist oder nicht gefunden werden kann, oder wenn der erstellte absolute Pfadname (`absPath`) länger ist als `maxLength`), gibt die Funktion `NULL` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_fullpath` Funktion erweitert den relativen Pfadnamen in `relPath` an ihre voll qualifizierten oder absolute Pfad und speichert diese Namen in `absPath`. Wenn `absPath` NULL ist, wird `malloc` verwendet, um einen Puffer zuzuweisen, der lang genug ist, um den Pfadnamen zu enthalten. Der Aufrufer muss diesen Puffer freigeben. Dieser relative Pfadname gibt vom aktuellen Speicherort einen Pfad zu einem anderen Speicherort an (z.B. das aktuelle Arbeitsverzeichnis: "."). Ein absoluter Pfadname ist die Erweiterung eines relativen Pfadnamens, der den gesamten Pfad ausdrückt, der dafür erforderlich ist, um die gewünschte Position aus dem Stammverzeichnis des Dateisystems zu erreichen. Im Gegensatz zu `_makepath` kann `_fullpath` dazu verwendet werden, um den absoluten Pfadnamen für relative Pfade (`relPath`) zu erhalten, die „./“ oder „../“ im Namen enthalten.  
  
 Um beispielsweise C-Laufzeitroutinen verwenden zu können, muss die Anwendung die Headerdateien enthalten, die die Deklarationen für die Routinen enthalten. Jede Headerdatei enthält Anweisungen, die relativ auf den Speicherort der Datei verweisen (aus dem Arbeitsverzeichnis der Anwendung):  
  
```  
#include <stdlib.h>  
```  
  
 Wenn der absolute Pfad (der tatsächliche Dateisystem-Speicherort) der Datei z.B. wie folgt lautet:  
  
```  
\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h  
```  
  
 `_fullpath` verarbeitet Multibyte-Zeichenfolgenargumente automatisch richtig. Die Erkennung von Multibyte-Zeichensequenzen erfolgt auf der Grundlage der aktuell verwendeten Multibyte-Codeseite. `_wfullpath` ist eine Breitzeichenversion von `_fullpath`. Die Zeichenfolgenargumente für `_wfullpath` sind Zeichenfolgen mit Breitzeichen. `_wfullpath` und `_fullpath` verhalten sich nahezu identisch, allerdings verarbeitet `_wfullpath` keine Multibyte-Zeichenfolgen.  
  
 Wenn sowohl `_DEBUG` als auch `_CRTDBG_MAP_ALLOC` definiert sind, werden Aufrufe von `_fullpath` und `_wfullpath` durch Aufrufe von `_fullpath_dbg` und `_wfullpath_dbg` ersetzt, um das Debuggen von Speicherbelegungen zuzulassen. Weitere Informationen finden Sie unter [_fullpath_dbg, _wfullpath_dbg](../../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md).  
  
 Diese Funktion ruft den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, wenn `maxlen` weniger gleich 0 ist. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `NULL` zurück.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfullpath`|`_fullpath`|`_fullpath`|`_wfullpath`|  
  
 Wenn der `absPath`-Puffer `NULL` ist,ruft `_fullpath` [malloc](../../c-runtime-library/reference/malloc.md) auf, um Puffer zuzuweisen, und ignoriert das `maxLength`-Argument. Es liegt in der Verantwortung des Aufrufers, die Zuordnung für diesen Puffer richtig wieder aufzuheben (mithilfe von [free](../../c-runtime-library/reference/free.md)). Wenn das `relPath`-Argument ein Laufwerk angibt, wird das aktuelle Verzeichnis dieses Laufwerks mit dem Pfad kombiniert.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_fullpath`|\<stdlib.h>|  
|`_wfullpath`|\<stdlib.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_fullpath.c  
// This program demonstrates how _fullpath  
// creates a full path from a partial path.  
  
#include <stdio.h>  
#include <conio.h>  
#include <stdlib.h>  
#include <direct.h>  
  
void PrintFullPath( char * partialPath )  
{  
   char full[_MAX_PATH];  
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )  
      printf( "Full path is: %s\n", full );  
   else  
      printf( "Invalid path\n" );  
}  
  
int main( void )  
{  
   PrintFullPath( "test" );  
   PrintFullPath( "\\test" );  
   PrintFullPath( "..\\test" );  
}  
```  
  
```Output  
Full path is: C:\Documents and Settings\user\My Documents\test  
Full path is: C:\test  
Full path is: C:\Documents and Settings\user\test  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdcwd, _wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)
