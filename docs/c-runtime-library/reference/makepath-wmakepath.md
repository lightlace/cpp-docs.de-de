---
title: _makepath, _wmakepath | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _makepath
- _wmakepath
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
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
dev_langs:
- C++
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: 22
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
ms.openlocfilehash: deb4333b36bf0b3eb2080d838ef3f23a052cf262
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="makepath-wmakepath"></a>_makepath, _wmakepath
Erstellen Sie einen Pfadnamen aus Komponenten. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
void _makepath(  
   char *path,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
void _wmakepath(  
   wchar_t *path,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `path`  
 Vollständiger Pfadpuffer  
  
 `drive`  
 Enthält einen Buchstaben (A, B usw.) für das gewünschte Laufwerk und einen optionalen nachgestellten Doppelpunkt. `_makepath` fügt den Doppelpunkt automatisch in den zusammengesetzten Pfad ein, wenn dieser nicht vorhanden ist. Wenn `drive` `NULL` darstellt oder auf eine leere Zeichenfolge verweist, erscheint kein Laufwerksbuchstabe in der zusammengesetzten `path`-Zeichenfolge.  
  
 `dir`  
 Enthält den Pfad der Verzeichnisse, ausgenommen die Laufwerkkennzeichner oder den tatsächlichen Dateinamen. Der nachstehende Schrägstrich ist optional, und entweder ein Schrägstrich (/) oder ein umgekehrter Schrägstrich (\\) oder beides kann in einem einzelnen `dir`-Argument verwendet werden. Wenn kein nachstehender Schrägstrich (/ oder \\) angegeben ist, wird er automatisch eingefügt. Wenn `dir` `NULL` ist oder auf eine leere Zeichenfolge verweist, wird kein Verzeichnispfad in die zusammengesetzte `path`-Zeichenfolge eingefügt.  
  
 `fname`  
 Enthält den Basisdateinamen ohne Dateinamenerweiterungen. Wenn `fname` `NULL` ist oder auf eine leere Zeichenfolge verweist, wird kein Dateiname in die zusammengesetzte `path`-Zeichenfolge eingefügt.  
  
 `ext`  
 Enthält die eigentliche Dateinamenerweiterung mit oder ohne führenden Punkt (.). `_makepath` fügt automatisch den Punkt ein, wenn er nicht in `ext` erscheint. Wenn `ext` `NULL` ist oder auf eine leere Zeichenfolge verweist, wird keine Dateiendung in die zusammengesetzte `path`-Zeichenfolge eingefügt.  
  
## <a name="remarks"></a>Hinweise  
 Die `_makepath`-Funktion erstellt eine zusammengesetzte Pfadzeichenfolge aus einzelnen Komponenten. Das Ergebnis wird in `path` gespeichert. Der `path` kann möglicherweise einen Laufwerkbuchstaben, einen Verzeichnispfad, einen Dateinamen sowie Dateinamenerweiterungen enthalten. `_wmakepath` ist eine Breitzeichenversion von `_makepath`. Die Argumente für `_wmakepath` sind Zeichenfolgen mit Breitzeichen. `_wmakepath` und `_makepath` verhalten sich andernfalls identisch.  
  
 **Sicherheitshinweis** Verwenden Sie eine mit NULL endende Zeichenfolge. Die mit NULL endende Zeichenfolge darf die Größe des `path`-Puffers nicht überschreiten, damit kein Pufferüberlauf verursacht wird. `_makepath` stellt nicht sicher, dass die Länge der Zeichenfolge für den zusammengesetzten Pfad nicht `_MAX_PATH` übersteigt. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmakepath`|`_makepath`|`_makepath`|`_wmakepath`|  
  
 Das `path`-Argument muss auf einen leeren Puffer verweisen, der groß genug ist, um den kompletten Pfad zu enthalten. Das kombinierte `path`-Argument darf nicht größer sein als die `_MAX_PATH`-Konstante, die in „Stdlib.h“ definiert ist.  
  
 Wenn der Pfad `NULL` ist, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Darüber hinaus wird `errno` auf `EINVAL` festgelegt. `NULL`-Werte sind für alle anderen Parameter zugelassen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_makepath`|\<stdlib.h>|  
|`_wmakepath`|\<stdlib.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_makepath.c  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
  
   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996  
   // Note: _makepath is deprecated; consider using _makepath_s instead  
   printf( "Path created with _makepath: %s\n\n", path_buffer );  
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996  
   // Note: _splitpath is deprecated; consider using _splitpath_s instead  
   printf( "Path extracted with _splitpath:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
```Output  
Path created with _makepath: c:\sample\crt\makepath.c  
  
Path extracted with _splitpath:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: makepath  
  Ext: .c  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)
