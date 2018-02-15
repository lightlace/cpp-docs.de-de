---
title: _creat _wcreat | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _creat
- _wcreat
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
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
dev_langs:
- C++
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0355f28ada6313e201b8d761813767135ee3cbf8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="creat-wcreat"></a>_creat, _wcreat
Erstellt eine neue Datei. `_creat`und `_wcreat` sind veraltet; verwenden Sie stattdessen [_sopen_s _wsopen_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _creat(   
   const char *filename,  
   int pmode   
);  
int _wcreat(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Name der neuen Datei.  
  
 `pmode`  
 Berechtigungseinstellung.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Funktionen, sofern erfolgreich, geben einen Dateideskriptor an die erstellte Datei zurück. Andernfalls, die Funktionen – 1 zurück und legen Sie `errno` wie in der folgenden Tabelle gezeigt.  
  
|`errno`-Einstellung|Beschreibung|  
|---------------------|-----------------|  
|`EACCES`|`filename` gibt eine vorhandene schreibgeschützte Datei oder ein Verzeichnis anstelle einer Datei an.|  
|`EMFILE`|Es sind keine Dateideskriptoren mehr verfügbar.|  
|`ENOENT`|Die angegebene Datei wurde nicht gefunden.|  
  
 Wenn `filename` NULL ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben -1 zurück.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_creat`-Funktion erstellt eine neue Datei oder öffnet und verkleinert eine vorhandene. `_wcreat` ist eine Breitzeichenversion von `_creat`. Das `filename`-Argument für `_wcreat` ist eine Breitzeichenfolge. `_wcreat` und `_creat` verhalten sich andernfalls identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 Wenn die von `filename` angegebene Datei nicht vorhanden ist, wird eine neue Datei mit der angegebenen Berechtigungseinstellung erstellt und zum Schreiben geöffnet. Wenn die Datei bereits vorhanden ist und die Berechtigungseinstellung das Schreiben ermöglicht, verkleinert `_creat` die Datei auf die Länge 0. Der bisherige Inhalt wird entfernt und die Datei zum Schreiben geöffnet. Die Berechtigungseinstellung `pmode` gilt nur für neu erstellte Dateien. Die neue Datei erhält die angegebene Berechtigungseinstellung, nachdem sie zum ersten Mal geschlossen wurde. Der ganzzahlige Ausdruck `pmode` enthält eine oder beide der folgenden Manifestkonstanten, die in SYS\Stat.h definiert sind: `_S_IWRITE` und `_S_IREAD`. Wenn beide Konstanten gegeben sind, werden sie mit dem bitweisen `OR`-Operator ( **&#124;** ) verbunden. Der Parameter `pmode` wird auf einen der folgenden Werte eingestellt:  
  
|Wert|Definition|  
|-----------|----------------|  
|`_S_IWRITE`|Schreiben zugelassen.|  
|`_S_IREAD`|Lesen erlaubt.|  
|`_S_IREAD &#124; _S_IWRITE`|Lesen und Schreiben erlaubt.|  
  
 Wenn keine Schreibberechtigung gewährt wird, kann die Datei nur gelesen werden. Hinweis: Alle Dateien sind stets lesbar; es ist nicht möglich, nur Schreibberechtigungen zu vergeben. Deshalb sind die Modi `_S_IWRITE` und `_S_IREAD | _S_IWRITE` gleichwertig. Mit `_creat` geöffnete Dateien werden immer im Kompatibilitätsmodus geöffnet (siehe [_sopen](../../c-runtime-library/reference/sopen-wsopen.md)) mit `_SH_DENYNO`.  
  
 `_creat` wendet die aktuelle Dateiberechtigungsmaske für `pmode` an, bevor die Berechtigungen (siehe [_umask](../../c-runtime-library/reference/umask.md)) festgelegt werden. `_creat` wird in erster Linie für die Kompatibilität mit früheren Bibliotheken bereitgestellt. Ein Aufruf von `_open` mit `_O_CREAT` und `_O_TRUNC` im `oflag`-Parameter entspricht `_creat` und empfiehlt sich für neuen Code .  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_creat`|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
|`_wcreat`|\<io.h> oder \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_creat.c  
// compile with: /W3  
// This program uses _creat to create  
// the file (or truncate the existing file)  
// named data and open it for writing.  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int fh;  
  
   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996  
   // Note: _creat is deprecated; use _sopen_s instead  
   if( fh == -1 )  
      perror( "Couldn't create data file" );  
   else  
   {  
      printf( "Created data file.\n" );  
      _close( fh );  
   }  
}  
```  
  
```Output  
Created data file.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_schließen](../../c-runtime-library/reference/close.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)