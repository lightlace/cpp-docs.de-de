---
title: _popen _wpopen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _popen
- _wpopen
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
- tpopen
- popen
- wpopen
- _popen
- _wpopen
- _tpopen
dev_langs:
- C++
helpviewer_keywords:
- tpopen function
- pipes, creating
- _popen function
- _tpopen function
- popen function
- wpopen function
- _wpopen function
ms.assetid: eb718ff2-c87d-4bd4-bd2e-ba317c3d6973
caps.latest.revision: 15
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
ms.openlocfilehash: f5cb8430c6539e7c16f38ae8cbac6016f7c85215
ms.lasthandoff: 02/24/2017

---
# <a name="popen-wpopen"></a>_popen, _wpopen
Erstellt eine Pipe und führt einen Befehl aus.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      FILE *_popen(  
const char *command,  
const char *mode   
);  
FILE *_wpopen(  
const wchar_t *command,  
const wchar_t *mode   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *command*  
 Befehl, der ausgeführt werden soll.  
  
 *mode*  
 Modus des zurückgegebenen Streams.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Stream zurück, der einem Ende der erstellten Pipe zugeordnet ist. Das andere Ende der Pipe ist der Standardeingabe oder Standardausgabe des erzeugten Befehls zugeordnet. Die Funktionen geben bei einem Fehler **NULL** zurück. Wenn der Fehler ein ungültiger Parameter ist, etwa wenn *command* oder *mode* ein NULL-Zeiger oder *mode* kein gültiger Modus ist, wird `errno` auf `EINVAL` festgelegt. Gültige Modi können Sie dem Abschnitt mit den Hinweisen entnehmen.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_popen`-Funktion erstellt eine Pipe und führt asynchron eine generierte Kopie des Befehlsprozessors mit der angegebenen Zeichenfolge *command* aus. Die Zeichenfolge *mode* gibt den angeforderten Zugriffstyp wie folgt an.  
  
 **"r"**  
 Der aufrufende Prozess kann die Standardausgabe des erzeugten Befehls mit dem zurückgegebenen Stream lesen.  
  
 **"w"**  
 Der aufrufende Prozess kann die Standardeingabe des erzeugten Befehls mit dem zurückgegebenen Stream schreiben.  
  
 **"b"**  
 Öffnen im binären Modus.  
  
 **"t"**  
 Öffnen im Textmodus.  
  
> [!NOTE]
>  Wenn die `_popen`-Funktion in einem Windows-Programm verwendet wird, gibt sie einen ungültigen Dateizeiger zurück, der dafür sorgt, dass das Programm für unbestimmte Zeit nicht mehr reagiert. `_popen` funktioniert in einer Konsolenanwendung. Wie Sie eine Windows-Anwendung erstellen, die Eingabe und Ausgabe umleitet, lesen Sie im Artikel [Creating a Child Process with Redirected Input and Output (Erstellen eines untergeordneten Prozesses mit umgeleiteter Eingabe und Ausgabe)](http://msdn.microsoft.com/library/windows/desktop/ms682499) in [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 `_wpopen` ist eine Breitzeichenversion von `_popen`. Das *path*-Argument für `_wpopen` ist eine Breitzeichenfolge. `_wpopen` und `_popen` verhalten sich andernfalls identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tpopen`|`_popen`|`_popen`|`_wpopen`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_popen`|\<stdio.h>|  
|`_wpopen`|\<stdio.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_popen.c  
/* This program uses _popen and _pclose to receive a   
 * stream of text from a system process.  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
  
   char   psBuffer[128];  
   FILE   *pPipe;  
  
        /* Run DIR so that it writes its output to a pipe. Open this  
         * pipe with read text attribute so that we can read it   
         * like a text file.   
         */  
  
   if( (pPipe = _popen( "dir *.c /on /p", "rt" )) == NULL )  
      exit( 1 );  
  
   /* Read pipe until end of file, or an error occurs. */  
  
   while(fgets(psBuffer, 128, pPipe))  
   {  
      printf(psBuffer);  
   }  
  
   /* Close pipe and print return value of pPipe. */  
   if (feof( pPipe))  
   {  
     printf( "\nProcess returned %d\n", _pclose( pPipe ) );  
   }  
   else  
   {  
     printf( "Error: Failed to read the pipe to the end.\n");  
   }  
}  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
 Bei dieser Ausgabe wird davon ausgegangen, dass das aktuelle Verzeichnis nur eine Datei mit der Dateierweiterung .c enthält.  
  
```  
 Volume in drive C is CDRIVE  
 Volume Serial Number is 0E17-1702  
  
 Directory of D:\proj\console\test1  
  
07/17/98  07:26p                   780 popen.c  
               1 File(s)            780 bytes  
                             86,597,632 bytes free  
  
Process returned 0  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [_pclose](../../c-runtime-library/reference/pclose.md)   
 [_pipe](../../c-runtime-library/reference/pipe.md)
