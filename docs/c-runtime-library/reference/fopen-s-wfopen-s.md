---
title: fopen_s, _wfopen_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfopen_s
- fopen_s
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
- fopen_s
- _tfopen_s
- _wfopen_s
dev_langs: C++
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
caps.latest.revision: "41"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3205577627967fa58c3fbc0d1318a48fc5525561
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fopens-wfopens"></a>fopen_s, _wfopen_s
Öffnet eine Datei. Diese Versionen von [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitserweiterungen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t fopen_s(   
   FILE** pFile,  
   const char *filename,  
   const char *mode   
);  
errno_t _wfopen_s(  
   FILE** pFile,  
   const wchar_t *filename,  
   const wchar_t *mode   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pFile`  
 Ein Zeiger auf den Dateizeiger, der den Zeiger auf die geöffnete Datei erhält.  
  
 [in] `filename`  
 Dateiname.  
  
 [in] `mode`  
 Zugriffstyp zulässig.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt. Weitere Informationen zu diesen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`pFile`|`filename`|`mode`|Rückgabewert|Inhalt von `pFile`|  
|-------------|----------------|------------|------------------|------------------------|  
|`NULL`|any|any|`EINVAL`|unverändert|  
|any|`NULL`|any|`EINVAL`|unverändert|  
|any|any|NULL|`EINVAL`|unverändert|  
  
## <a name="remarks"></a>Hinweise  
 Dateien, die von `fopen_s` und `_wfopen_s` geöffnet werden, können nicht freigegeben werden. Wenn eine Datei freigegeben werden soll, verwenden Sie [_fsopen, _wfsopen](../../c-runtime-library/reference/fsopen-wfsopen.md) mit der entsprechenden Freigabemoduskonstanten: z.B. `_SH_DENYNO` für die Lese-/Schreibfreigabe.  
  
 Die `fopen_s`-Funktion öffnet die Datei, die von `filename` angegeben wird. `_wfopen_s` ist eine Breitzeichenversion von `fopen_s`. Die Argumente für `_wfopen_s` sind Zeichenfolgen mit Breitzeichen. `_wfopen_s` und `fopen_s` verhalten sich andernfalls identisch.  
  
 `fopen_s` akzeptiert Pfade, die zum Zeitpunkt der Ausführung im Dateisystem gültig sind. UNC-Pfade und Pfade mit zugeordneten Netzlaufwerken werden von `fopen_s` akzeptiert, solange das System, das den Code ausführt, zum Zeitpunkt der Ausführung Zugriff auf die Freigabe oder das zugeordnete Netzlaufwerk hat. Wenn Sie Pfade für `fopen_s` erstellen, machen Sie keine Annahmen über die Verfügbarkeit von Laufwerken, Pfaden oder Netzwerkfreigaben in der Ausführungsumgebung. Als Verzeichnistrennzeichen in einem Pfad können Sie entweder den Schrägstrich (/) oder den umgekehrten Schrägstrich (\\) verwenden.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `pFile`, `filename` oder `mode` ein NULL-Zeiger sind, generieren diese Funktionen eine Ausnahme wegen eines ungültigen Parameters, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
 Überprüfen Sie stets den Rückgabewert, um festzustellen, ob die Funktion erfolgreich war, bevor Sie mit der Datei andere Vorgänge ausführen. Wenn ein Fehler auftritt, wird der Fehlercode zurückgegeben und die globale Variable `errno` wird festgelegt. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="unicode-support"></a>Unterstützung für Unicode  
 `fopen_s` unterstützt Unicode-Dateistreams. Um eine neue oder vorhandene Unicode-Datei zu öffnen, geben Sie ein `ccs`-Flag, das die gewünschte Codierung angibt, an `fopen_s` weiter:  
  
 `fopen_s(&fp, "newfile.txt", "rw, ccs=`*Codierung*`");`  
  
 Zulässige Werte von *Codierung* sind `UNICODE`, `UTF-8`, und `UTF-16LE`. Wenn es kein Wert angegeben wird, für die *Codierung*, `fopen_s` ANSI-Codierung verwendet.  
  
 Wenn die Datei bereits vorhanden ist und zum Lesen oder Anhängen geöffnet ist, bestimmt die Bytereihenfolge-Marke (BOM), sofern in der Datei vorhanden, die Codierung. Die BOM-Codierung hat Vorrang vor der durch das `ccs`-Flag angegebenen Codierung. Die `ccs`-Codierung wird nur verwendet, wenn keine BOM vorhanden ist oder wenn die Datei neu ist.  
  
> [!NOTE]
>  Die BOM-Erkennung gilt nur für Dateien, die im Unicode-Modus geöffnet sind, das heißt durch Übergeben des `ccs`-Flags.  
  
 Die folgende Tabelle fasst die Modi für verschiedene `ccs`-Flags für `fopen_s` sowie für die Bytereihenfolge-Marken in der Datei zusammen.  
  
### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>Verwendete Codierungen auf Grundlage von ccs-Flag und BOM  
  
|`ccs` -Flag|Keine BOM (oder neue Datei)|BOM: UTF-8|BOM: UTF-16|  
|----------------|----------------------------|-----------------|------------------|  
|`UNICODE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
|`UTF-8`|`UTF-8`|`UTF-8`|`UTF-16LE`|  
|`UTF-16LE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
  
 In Dateien, die zum Schreiben im Unicode-Modus geöffnet werden, wird automatisch eine BOM geschrieben.  
  
 Wenn `mode` wird "a, ccs =*Codierung*", `fopen_s` versucht zuerst, die Datei mit Lesezugriff und Schreibzugriff zu öffnen. Ist der Vorgang erfolgreich, liest die Funktion die BOM, um die Codierung für die Datei zu bestimmen. Schlägt der Vorgang fehl, verwendet die Funktion die Standardcodierung für die Datei. In jedem Fall öffnet `fopen_s` dann die Datei nur mit Schreibzugriff erneut. (Dies gilt nur für den `a`-Modus, nicht für `a+`.)  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfopen_s`|`fopen_s`|`fopen_s`|`_wfopen_s`|  
  
 Die Zeichenfolge `mode` gibt die Art des Zugriffs, der für die Datei angefordert wird, wie folgt an.  
  
 `"r"`  
 Öffnet zum Lesen. Wenn die Datei nicht vorhanden ist oder nicht gefunden werden kann, schlägt der `fopen_s` -Aufruf fehl.  
  
 `"w"`  
 Öffnet eine leere Datei zum Schreiben. Wenn die Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 `"a"`  
 Wird vor dem Schreiben neuer Daten in die Datei zum Schreiben am Ende der Datei (Anfügen) geöffnet, ohne die EOF-Markierung zu entfernen. Erstellt die Datei, wenn sie nicht vorhanden ist.  
  
 `"r+"`  
 Öffnet sowohl zum Lesen als auch zum Schreiben. (Die Datei muss vorhanden sein.)  
  
 `"w+"`  
 Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 `"a+"`  
 Öffnet sich zum Lesen und Anfügen. Der Anfügevorgang umfasst das Entfernen des EOF-Markers, bevor neue Daten in die Datei geschrieben werden. Nachdem der Schreibvorgang abgeschlossen ist, wird die EOF-Markierung wiederhergestellt. Erstellt die Datei, wenn sie nicht vorhanden ist.  
  
 Bei einer mit dem Zugriffstyp `"a"` oder `"a+"` geöffneten Datei erfolgen alle Schreibvorgänge am Ende der Datei. Der Dateizeiger kann mit `fseek` oder `rewind` neu angeordnet werden. Er wird jedoch immer wieder zurück an das Ende der Datei verschoben, noch bevor der Schreibvorgang ausgeführt wird, damit vorhandene Daten nicht überschrieben werden können.  
  
 Bei dem Modus `"a"` wird die EOF-Markierung nicht entfernt, bevor Daten an die Datei angefügt werden. Nach dem Anfügen werden durch den MS-DOS-Befehl TYPE nur Daten bis zur ursprünglichen EOF-Markierung angezeigt, aber keine Daten, die an die Datei angefügt wurden. Bei dem Modus `"a+"` wird die EOF-Markierung entfernt, bevor Daten an die Datei angefügt werden. Nach dem Anhängen werden mit dem Befehl MS-DOS TYPE alle Daten in der Datei angezeigt. Der Modus `"a+"` ist für das Anfügen von Daten an eine Streamdatei erforderlich, die mit der EOF-Markierung STRG+Z beendet wird.  
  
 Wenn die `"r+"`, `"w+",` oder `"a+"` Zugriff angegeben wird, sind sowohl Lese-als auch Schreibvorgänge zulässig. (Die Datei ist dann für ein "Update" geöffnet.) Wenn Sie jedoch vom Lesevorgang in den Schreibvorgang wechseln, muss die Eingabeoperation eine EOF-Markierung antreffen. Wenn keine EOF-Markierung vorhanden ist, müssen Sie einen zwischenzeitlichen Aufruf einer dateipositionierenden Funktion verwenden. Die dateipositionierenden Funktionen sind `fsetpos`, `fseek` und `rewind`. Wenn Sie vom Schreibvorgang in den Lesevorgang wechseln, müssen Sie einen zwischenzeitlichen Aufruf von `fflush` oder einer dateipositionierenden Funktion ausführen.  
  
 Neben den obigen Werte können die folgenden Zeichen in `mode` enthalten sein, um den Übersetzungsmodus für Zeilenumbruchzeichen anzugeben:  
  
 `t`  
 Öffnen im Textmodus (übersetzt). In diesem Modus wird STRG+Z als Dateiendezeichen bei Eingabe interpretiert. In den Dateien, die für das Lesen/Schreiben mit `"a+"` geöffnet sind, überprüft `fopen_s` die Datei auf STRG+Z am Dateiende, und entfernt sofern möglich die Markierung. Dies geschieht, da ein Verwenden von `fseek` und `ftell` zum Navigieren innerhalb einer Datei, die mit Strg+Z endet, dazu führen kann, dass sich `fseek` in der Nähe des Dateiendes nicht ordnungsgemäß verhält.  
  
 Darüber hinaus wird im Textmodus Carriage Return-Zeilenvorschub-Kombinationen in einzelne Zeilenvorschübe bei Eingabe übersetzt, und Zeilenvorschubzeichen in Carriage Return-Zeilenvorschub-Kombinationen bei der Ausgabe übersetzt werden. Wenn eine Stream-E/A-Funktion von Unicode im Textmodus (Standard) funktioniert, wird angenommen, dass es sich bei Quell- oder Zielstream um eine Sequenz von Multibytezeichen handelt. Daher konvertieren die Unicode Streameingabefunktionen Multibytezeichen in Breitzeichen (wie bei einem Aufruf der `mbtowc` -Funktion). Aus demselben Grund konvertieren die Unicode-Streamausgabefunktionen Breitzeichen in Multibytezeichen (wie bei einem Aufruf der `wctomb` -Funktion).  
  
 `b`  
 Öffnen im binären (unübersetzten) Modus; Übersetzungen von Wagenrücklauf- und Zeilenvorschubzeichen werden unterdrückt.  
  
 Wenn `t` oder `b` nicht in `mode`angegeben ist, wird der Standardübersetzungsmodus durch die globale Variable [_fmode](../../c-runtime-library/fmode.md)definiert. Wenn dem Argument `t` oder `b` vorangestellt wird, schlägt die Funktion fehl und gibt `NULL`zurück.  
  
 Weitere Informationen zur Anwendung von Text- und Binärmodi in Unicode- und Multibyte-Stream-E/A finden Sie unter [Text- und Binärmodusdatei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [Unicodestream-E/A im Text- und Binärmodus](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
 `c`  
 Aktivieren Sie das Commitflag für den zugeordneten Parameter `filename` , sodass der Inhalt des Dateipuffers direkt auf einen Datenträger geschrieben wird, wenn `fflush` oder `_flushall` aufgerufen wird.  
  
 `n`  
 Setzen Sie das Commitflag für den zugeordneten Parameter `filename` auf "no-commit" zurück. Dies ist die Standardeinstellung. Dabei wird auch das globale Commitflag überschrieben, wenn Sie das Programm mit COMMODE.OBJ verknüpfen. Der Standardwert des globalen Commitflags lautet "no-commit", es sei denn, Sie verknüpfen das Programm explizit mit COMMODE.OBJ (siehe [Link Options](../../c-runtime-library/link-options.md)).  
  
 `N`  
 Gibt an, dass die Datei nicht von untergeordneten Prozessen geerbt wird.  
  
 `S`  
 Gibt an, dass das Zwischenspeichern für den sequenziellen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.  
  
 `R`  
 Gibt an, dass das Zwischenspeichern für den zufälligen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.  
  
 `T`  
 Gibt an, dass eine Datei temporär ist. Wenn möglich, wird sie nicht auf den Datenträger geschrieben.  
  
 `D`  
 Gibt an, dass eine Datei temporär ist. Sie wird gelöscht, wenn der letzte Dateizeiger geschlossen wird.  
  
 `ccs=ENCODING`  
 Geben Sie den für diese Datei zu verwendenden codierten Zeichensatz an (UTF-8, UTF-16LE und UNICODE). Machen Sie keine Angabe, wenn Sie ANSI-Codierung wünschen.  
  
 Gültige Zeichen für die `mode`-Zeichenfolge, die in `fopen_s` und `_fdopen` verwendet wird, entsprechen `oflag`-Argumenten, die in [_open](../../c-runtime-library/reference/open-wopen.md) und [_sopen](../../c-runtime-library/reference/sopen-wsopen.md) verwendet werden (siehe unten).  
  
|Zeichen in der mode-Zeichenfolge|Der entsprechende `oflag` -Wert für `_open`/`_sopen`|  
|-------------------------------|----------------------------------------------------|  
|`a`|`_O_WRONLY &#124; _O_APPEND` (meistens `_O_WRONLY &#124; _O_CREAT &#124; _O_APPEND`)|  
|`a+`|`_O_RDWR &#124; _O_APPEND` (meistens `_O_RDWR &#124; _O_APPEND &#124; _O_CREAT` )|  
|`r`|`_O_RDONLY`|  
|`r+`|`_O_RDWR`|  
|`w`|`_O_WRONLY` (meistens `_O_WRONLY &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`w+`|`_O_RDWR` (meistens `_O_RDWR &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`b`|`_O_BINARY`|  
|`t`|`_O_TEXT`|  
|`c`|Keine|  
|`n`|Keiner|  
|`S`|`_O_SEQUENTIAL`|  
|`R`|`_O_RANDOM`|  
|`T`|`_O_SHORTLIVED`|  
|`D`|`_O_TEMPORARY`|  
|`ccs=UNICODE`|`_O_WTEXT`|  
|`ccs=UTF-8`|`_O_UTF8`|  
|`ccs=UTF-16LE`|`_O_UTF16`|  
  
 Wenn Sie den `rb`-Modus verwenden, den Code nicht portieren müssen und davon ausgehen, einen Großteil der Datei zu lesen, und/oder die Netzwerkleistung irrelevant ist, sind möglicherweise Win32-Dateien mit Speicherzuordnung auch eine Option.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`fopen_s`|\<stdio.h>|  
|`_wfopen_s`|\<stdio.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md)  
  
 Die `mode`-Optionen `c`, `n`, und `t` sind Microsoft-Erweiterungen für `fopen_s` und `_fdopen` und sollten nicht dort verwendet werden, wo ANSI-Portabilität gewünscht wird.  
  
## <a name="example"></a>Beispiel  
  
```C  
// crt_fopen_s.c  
// This program opens two files. It uses  
// fclose to close the first file and  
// _fcloseall to close all remaining files.  
  
#include <stdio.h>  
  
FILE *stream, *stream2;  
  
int main( void )  
{  
   errno_t err;  
  
   // Open for read (will fail if file "crt_fopen_s.c" does not exist)  
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );  
   if( err == 0 )  
   {  
      printf( "The file 'crt_fopen_s.c' was opened\n" );  
   }  
   else  
   {  
      printf( "The file 'crt_fopen_s.c' was not opened\n" );  
   }  
  
   // Open for write   
   err = fopen_s( &stream2, "data2", "w+" );  
   if( err == 0 )  
   {  
      printf( "The file 'data2' was opened\n" );  
   }  
   else  
   {  
      printf( "The file 'data2' was not opened\n" );  
   }  
  
   // Close stream if it is not NULL   
   if( stream )  
   {  
      err = fclose( stream );  
      if ( err == 0 )  
      {  
         printf( "The file 'crt_fopen_s.c' was closed\n" );  
      }  
      else  
      {  
         printf( "The file 'crt_fopen_s.c' was not closed\n" );  
      }  
   }  
  
   // All other files are closed:  
   int numclosed = _fcloseall( );  
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );  
}  
```  
  
```Output  
The file 'crt_fopen_s.c' was opened  
The file 'data2' was opened  
Number of files closed by _fcloseall: 1  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)