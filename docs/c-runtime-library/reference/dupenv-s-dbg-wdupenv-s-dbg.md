---
title: "_dupenv_s_dbg, _wdupenv_s_dbg"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_dupenv_s_dbg"
  - "_wdupenv_s_dbg"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tdupenv_s_dbg"
  - "_dupenv_s_dbg"
  - "_wdupenv_s_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tdupenv_s_dbg-Funktion"
  - "dupenv_s_dbg-Funktion"
  - "_wdupenv_s_dbg-Funktion"
  - "Umgebungsvariablen"
  - "tdupenv_s_dbg-Funktion"
  - "wdupenv_s_dbg-Funktion"
  - "_dupenv_s_dbg-Funktion"
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# _dupenv_s_dbg, _wdupenv_s_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft einen Wert aus der aktuellen Umgebung ab.  Versionen von [\_dupenv\_s, \_wdupenv\_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md), die Speicher mit [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md) belegen, um zusätzliche Debuginformationen bereitzustellen.  
  
## Syntax  
  
```  
errno_t _dupenv_s_dbg(  
   char **buffer,  
   size_t *numberOfElements,  
   const char *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
errno_t _wdupenv_s_dbg(  
   wchar_t **buffer,  
   size_t * numberOfElements,  
   const wchar_t *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
```  
  
#### Parameter  
 `buffer`  
 Puffer zum Speichern des Variablenwerts.  
  
 `numberOfElements`  
 Größe von `buffer`.  
  
 `varname`  
 Umgebungsvariablenname.  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger zum Namen der Quelldatei oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei oder `NULL`.  
  
## Rückgabewert  
 Null bei Erfolg, ein Fehlercode, wenn ein Fehler auftritt.  
  
 Diese Funktionen überprüfen ihre Parameter; wenn `buffer` oder `varname``NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, legen die Funktionen `errno` auf `EINVAL` fest und geben `EINVAL` zurück.  
  
 Wenn diese Funktionen nicht genug Arbeitsspeicher zuordnen können, legen sie `buffer` auf `NULL` und `numberOfElements` auf 0 fest und geben `ENOMEM` zurück.  
  
## Hinweise  
 Die `_dupenv_s_dbg`\- und `_wdupenv_s_dbg`\-Funktionen sind identisch mit `_dupenv_s` und `_wdupenv_s`, außer dass bei Definition von `_DEBUG` diese Funktionen die Debugversion von [malloc](../../c-runtime-library/reference/malloc.md), [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md) verwenden, um Speicher für den Wert der Umgebungsvariable zu belegen.  Weitere Informationen zu den Debugfunktionen von `_malloc_dbg` finden Sie unter [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen.  Stattdessen können Sie das `_CRTDBG_MAP_ALLOC`\-Flag definieren.  Wenn `_CRTDBG_MAP_ALLOC` definiert ist, werden Aufrufe von `_dupenv_s` und `_wdupenv_s` zu `_dupenv_s_dbg` bzw. `_wdupenv_s_dbg` neu zugeordnet, wobei `blockType` auf `_NORMAL_BLOCK` festgelegt wird.  Daher müssen Sie diese Funktionen nicht explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als `_CLIENT_BLOCK` markieren.  Weitere Informationen zu den Blocktypen finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tdupenv_s_dbg`|`_dupenv_s_dbg`|`_dupenv_s_dbg`|`_wdupenv_s_dbg`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_dupenv_s_dbg`|\<crtdbg.h\>|  
|`_wdupenv_s_dbg`|\<crtdbg.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_dupenv_s_dbg.c  
#include  <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s_dbg( &pValue, &len, "pathext",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s_dbg( &pValue, &len, "nonexistentvariable",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## Beispielausgabe  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## .NET Framework-Entsprechung  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [Umgebungskonstanten](../../c-runtime-library/environmental-constants.md)   
 [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)