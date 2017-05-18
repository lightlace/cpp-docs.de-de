---
title: _fsopen, _wfsopen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfsopen
- _fsopen
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
- wfsopen
- fsopen
- tfsopen
- _tfsopen
- _wfsopen
- _fsopen
dev_langs:
- C++
helpviewer_keywords:
- opening files, streams
- fsopen function
- tfsopen function
- wfsopen function
- _fsopen function
- files [C++], opening
- _tfsopen function
- _wfsopen function
- file sharing [C++]
ms.assetid: 5e4502ab-48a9-4bee-a263-ebac8d638dec
caps.latest.revision: 20
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: c53bdd4bdd5d6707e6da15def20b6375dcf6e0dd
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="fsopen-wfsopen"></a>_fsopen, _wfsopen
Ein Stream mit Dateifreigabe öffnen  
  
## <a name="syntax"></a>Syntax  
  
```  
FILE *_fsopen(   
   const char *filename,  
   const char *mode,  
   int shflag   
);  
FILE *_wfsopen(   
   const wchar_t *filename,  
   const wchar_t *mode,  
   int shflag   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Name der zu öffnenden Datei.  
  
 `mode`  
 Zugriffstyp zulässig.  
  
 `shflag`  
 Freigabetyp erlaubt.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf den Stream zurück. Ein NULL-Zeigerwert gibt einen Fehler an. Wenn `filename` oder `mode` `NULL` oder eine leere Zeichenfolge ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `NULL` zurück und stellen `errno` auf `EINVAL`ein.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_fsopen` öffnet die durch `filename` als Stream angegebene Datei und bereitet sie zur Lese- oder Schreibfreigabe vor, wie durch Modus und `shflag` Argumente definiert. `_wfsopen` ist eine Breitzeichenversion von `_fsopen`. Die `filename` und `mode` Argumente für `_wfsopen` sind Zeichenfolgen mit Breitzeichen. `_wfsopen` und `_fsopen` verhalten sich andernfalls identisch.  
  
 Die Zeichenfolge `mode` gibt den Typ des Zugriffs, der für die Datei angefordert wird, wie in der folgenden Tabelle gezeigt, an.  
  
|Begriff|Definition|  
|----------|----------------|  
|`"r"`|Öffnet zum Lesen. Wenn die Datei nicht vorhanden ist oder nicht gefunden werden kann, schlägt der `_fsopen` -Aufruf fehl.|  
|`"w"`|Öffnet eine leere Datei zum Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.|  
|`"a"`|Öffnet zum Schreiben am Ende der Datei (Anfügen); erstellt die Datei zuerst, wenn sie nicht vorhanden ist.|  
|`"r+"`|Öffnet sowohl zum Lesen als auch zum Schreiben. (Die Datei muss vorhanden sein.)|  
|`"w+"`|Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.|  
|`"a+"`|Öffnet zum Lesen und Anhängen; erstellt die Datei zuerst, wenn sie nicht vorhanden ist.|  
  
 Die Typen `"w"` und `"w+"` sind mit Vorsicht zu verwenden, da sie vorhandene Dateien zerstören können.  
  
 Bei einer mit dem Zugriffstyp `"a"` oder `"a+"` geöffneten Datei erfolgen alle Schreibvorgänge am Ende der Datei. Der Dateizeiger kann mit `fseek` oder `rewind` neu angeordnet werden, er wird jedoch immer wieder zurück an das Ende der Datei verschoben, bevor ein Schreibvorgang durchgeführt wird. Folglich können vorhandene Daten nicht überschrieben werden. Wenn als Zugriffstyp `"r+"`, `"w+"` oder `"a+"` angegeben wird, sind sowohl Lese- als auch Schreibvorgänge zulässig (die Datei ist zum Aktualisieren geöffnet). Wenn Sie jedoch zwischen Lesen und Schreiben wechseln, muss ein sich dazwischen befindender Vorgang wie [fsetpos](../../c-runtime-library/reference/fsetpos.md), [fseek](../../c-runtime-library/reference/fseek-fseeki64.md) oder [rewind](../../c-runtime-library/reference/rewind.md) vorhanden sein. Bei Bedarf kann die aktuelle Position für den Vorgang `fsetpos` oder `fseek` angegeben werden. Zusätzlich zu den oben aufgeführten Werten kann eines der folgenden Zeichen in `mode` enthalten sein, um den Übersetzungsmodus für neue Zeilen anzugeben und für Dateiverwaltung.  
  
|Begriff|Definition|  
|----------|----------------|  
|`t`|Öffnet eine Datei im Textmodus (übersetzt). Klicken Sie in diesem Modus Carriage Return Line feed (CR-LF) Kombinationen bei der Eingabe in einzelne Zeilenvorschübe (LF) übersetzt, und bei Ausgabe in CR-LF-Kombinationen aus LF-Zeichen übersetzt. Außerdem wird STRG+Z bei der Eingabe als EOF-Zeichen interpretiert. In den Dateien, die für das Lesen oder Lesen/Schreiben geöffnet sind, überprüft `_fsopen` die Datei auf STRG+Z am Dateiende, und entfernt sofern möglich die Markierung. Dies geschieht, da ein Verwenden von `fseek` und `ftell` zum Navigieren innerhalb einer Datei, die mit Strg+Z endet, dazu führen kann, dass sich `fseek` in der Nähe des Dateiendes nicht ordnungsgemäß verhält.|  
|`b`|Öffnet im (unübersetzten) Binärmodus eine Datei; die oben genannten Übersetzungen werden unterdrückt.|  
|`S`|Gibt an, dass das Zwischenspeichern für den sequenziellen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.|  
|`R`|Gibt an, dass das Zwischenspeichern für den zufälligen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.|  
|`T`|Gibt an, dass eine Datei temporär ist. Wenn möglich, wird sie nicht auf den Datenträger geschrieben.|  
|`D`|Gibt an, dass eine Datei temporär ist. Sie wird gelöscht, wenn der letzte Dateizeiger geschlossen wird.|  
  
 Wenn `t` oder `b` nicht in `mode` angegeben ist, wird der Standardübersetzungsmodus durch die Standardmodusvariable `_fmode` definiert. Wenn dem Argument `t` oder `b` vorangestellt wird, schlägt die Funktion fehl und gibt `NULL`zurück. Eine Erörterung von Text- und Binärmodi finden Sie unter [Text- und Binärmodusdatei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
 Das Argument `shflag` ist ein konstanter Ausdruck, der aus einer der folgenden Manifestkonstanten besteht, die in Share.h definiert sind.  
  
|Begriff|Definition|  
|----------|----------------|  
|`_SH_COMPAT`|Legt den Kompatibilitätsmodus für 16-Bit-Anwendungen fest.|  
|`_SH_DENYNO`|Erlaubt Lese- und Schreibzugriff.|  
|`_SH_DENYRD`|Verweigert den Lesezugriff auf die Datei.|  
|`_SH_DENYRW`|Verweigert den Lese- und Schreibzugriff auf die Datei.|  
|`_SH_DENYWR`|Verweigert den Lesezugriff auf die Datei.|  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfsopen`|`_fsopen`|`_fsopen`|`_wfsopen`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|Optionale Header|  
|--------------|---------------------|----------------------|  
|`_fsopen`|\<stdio.h>|\<share.h><br /><br /> Für die Manifestkonstante für `shflag` Parameter.|  
|`_wfsopen`|\<stdio.h> oder \<wchar.h>|\<share.h><br /><br /> Für die Manifestkonstante für `shflag` Parameter.|  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_fsopen.c  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <share.h>  
  
int main( void )  
{  
   FILE *stream;  
  
   // Open output file for writing. Using _fsopen allows us to  
   // ensure that no one else writes to the file while we are  
   // writing to it.  
    //  
   if( (stream = _fsopen( "outfile", "wt", _SH_DENYWR )) != NULL )  
   {  
      fprintf( stream, "No one else in the network can write "  
                       "to this file until we are done.\n" );  
      fclose( stream );  
   }  
   // Now others can write to the file while we read it.  
   system( "type outfile" );  
}  
```  
  
```Output  
No one else in the network can write to this file until we are done.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)
