---
title: "_creat, _wcreat | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_creat"
  - "_wcreat"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wcreat"
  - "_wcreat"
  - "_creat"
  - "tcreat"
  - "_tcreat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wcreat-Funktion"
  - "_wcreat-Funktion"
  - "Dateien [C++], Erstellen"
  - "_creat-Funktion"
  - "tcreat-Funktion"
  - "creat-Funktion"
  - "_tcreat-Funktion"
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _creat, _wcreat
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt eine neue Datei.  `_creat` und `_wcreat` sind veraltet; Verwenden Sie stattdessen [\_sopen\_s, \_wsopen\_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md).  
  
## Syntax  
  
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
  
#### Parameter  
 `filename`  
 Name der neuen Datei.  
  
 `pmode`  
 Berechtigungseinstellung.  
  
## Rückgabewert  
 Diese Funktionen, wenn erfolgreich, geben einen Dateideskriptor zur erstellten Datei zurück.  Andernfalls geben die Funktionen \- 1 und festgelegtem `errno` wie in der folgenden Tabelle dargestellt zurück.  
  
|Einstellung für `errno`|**Beschreibung**|  
|-----------------------------|----------------------|  
|`EACCES`|`filename` gibt eine vorhandene schreibgeschützte Datei an oder wird ein Verzeichnis und eine Datei an.|  
|`EMFILE`|Nicht mehr Dateideskriptoren sind verfügbar.|  
|`ENOENT`|Angegebene Datei wurde nicht gefunden.|  
  
 Wenn `filename` NULL ist, rufen diese Funktionen den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben – 1 zurück.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_creat`\-Funktion erstellt eine neue Datei oder öffnet und entfernt vorhandenes ab.  `_wcreat` ist eine Breitzeichenversion von `_creat`. Das `filename`\-Argument für `_wcreat` ist eine Breitzeichenfolge.  `_wcreat` und `_creat` verhalten sich andernfalls identisch.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 Wenn die Datei, die von `filename` angegeben wird, nicht vorhanden ist, wird eine neue Datei mit der angegebenen Berechtigungseinstellung erstellt und ist zum Schreiben geöffnet.  Wenn die Datei bereits vorhanden ist und die Berechtigungseinstellung Schreiben zulässt, schneidet `_creat` die Datei zu Länge 0 ab und zerstört vorherigen Inhalt, und öffnet sie zum Schreiben.  Die Berechtigungseinstellung, `pmode`, gilt nur neu erstellte Dateien zu.  Die neue Datei erhält die angegebene Berechtigungseinstellung, nachdem sie zum ersten Mal geschlossen ist.  Der ganzzahlige Ausdruck `pmode` enthält eine oder beide der Manifestkonstanten `_S_IWRITE` und `_S_IREAD`, die in SYS\\Stat.h.  Wenn beide Konstanten angegeben werden, sind sie mit dem bitweisen Operator `OR` verknüpft \(  **&#124;**\).  Der Parameter `pmode` wird auf einen der folgenden Werte festgelegt.  
  
|Wert|Definition|  
|----------|----------------|  
|`_S_IWRITE`|Schreiben zulässig.|  
|`_S_IREAD`|Lesen zulässig.|  
|`_S_IREAD &#124; _S_IWRITE`|Lesen und Schreiben zulässig.|  
  
 Wenn Schreibberechtigung nicht angegeben wird, ist die Datei schreibgeschützt.  Alle Dateien sind immer lesbar; Es ist nicht möglich, lesegeschützte Berechtigung zu geben.  Die Modi `_S_IWRITE``_S_IREAD` und `| _S_IWRITE` sind dann entsprechend.  Die Dateien, die mit `_creat` geöffnet sind, werden immer im Kompatibilitätsmodus \(siehe [\_sopen](../../c-runtime-library/reference/sopen-wsopen.md)\), mit `_SH_DENYNO` geöffnet.  
  
 `_creat` Übernimmt die aktuelle Dateiberechtigungsmaske zu `pmode`, bevor die Berechtigungen festzulegen \(siehe [\_umask](../../c-runtime-library/reference/umask.md)\).  `_creat` wird hauptsächlich für die Kompatibilität mit früheren Bibliotheken bereitgestellt.  Ein Aufruf von `_open` mit `_O_CREAT` und `_O_TRUNC` im `oflag`\-Parameter entspricht `_creat` und ist für neuen Code vorzuziehen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_creat`|\<io.h\>|\<sys\/types.h, sys\>\<\/stat.h, errno.h\>\<\>|  
|`_wcreat`|\<io.h oder\> wchar.h \<\>|\<sys\/types.h, sys\>\<\/stat.h, errno.h\>\<\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
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
  
  **Erstellte Datendatei.**   
## Siehe auch  
 [E\/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_sopen, \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [\_umask](../../c-runtime-library/reference/umask.md)