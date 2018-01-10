---
title: _sopen_s, _wsopen_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _sopen_s
- _wsopen_s
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
- _sopen_s
- wsopen_s
- _wsopen_s
- sopen_s
dev_langs: C++
helpviewer_keywords:
- sopen_s function
- _wsopen_s function
- wsopen_s function
- opening files, for sharing
- files [C++], opening
- _sopen_s function
- files [C++], sharing
ms.assetid: 059a0084-d08c-4973-9174-55e391b72aa2
caps.latest.revision: "29"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 403fc7f285aeebf5fc7b6d4ebb39d1e922d8edc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sopens-wsopens"></a>_sopen_s, _wsopen_s
Öffnet eine Datei zur Freigabe. Diese Versionen von [_sopen und _wsopen](../../c-runtime-library/reference/sopen-wsopen.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _sopen_s(  
   int* pfh,  
   const char *filename,  
   int oflag,  
   int shflag,  
   int pmode  
);  
errno_t _wsopen_s(  
   int* pfh,  
   const wchar_t *filename,  
   int oflag,  
   int shflag,  
   int pmode,  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pfh`  
 Das Dateihandle oder -1 im Fall eines Fehlers.  
  
 [in] `filename`  
 Dateiname  
  
 [in] `oflag`  
 Die Art der zulässigen Vorgänge.  
  
 [in] `shflag`  
 Die Art der zulässigen Freigabe.  
  
 [in] `pmode`  
 Berechtigungseinstellung.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Rückgabewert ungleich Null weist auf einen Fehler hin. In diesem Fall wird `errno` auf einen der folgenden Werte festgelegt.  
  
 `EACCES`  
 Der angegebene Pfad ist ein Verzeichnis, oder die Datei ist schreibgeschützt, aber es wurde versucht, einen Vorgang für das Öffnen zum Schreiben durchzuführen.  
  
 `EEXIST`  
 `_O_CREAT`- und `_O_EXCL`-Flag wurden angegeben, aber `filename` ist bereits vorhanden.  
  
 `EINVAL`  
 Ungültiges `oflag`-, `shflag`- oder `pmode`-Argument, oder `pfh` oder `filename` war ein NULL-Zeiger.  
  
 `EMFILE`  
 Es sind keine Dateideskriptoren mehr verfügbar.  
  
 `ENOENT`  
 Datei oder Pfad nicht gefunden.  
  
 Wenn ein ungültiges Argument an die Funktion übergeben wird, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` festgelegt und `EINVAL` zurückgegeben.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Im Fall eines Fehlers wird -1 über `pfh` zurückgegeben (es sein denn, `pfh` ist ein NULL-Zeiger).  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_sopen_s` öffnet die durch `filename` angegebene Datei und bereitet sie zur Lese- oder Schreibfreigabe vor, wie in `oflag` und `shflag` definiert. `_wsopen_s` ist eine Breitzeichenversion von `_sopen_s`. Das `filename`-Argument für `_wsopen_s` ist eine Breitzeichenfolge. `_wsopen_s` und `_sopen_s` verhalten sich andernfalls identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsopen_s`|`_sopen_s`|`_sopen_s`|`_wsopen_s`|  
  
 Der Ganzzahlausdruck `oflag` wird durch das Kombinieren einer oder mehrerer Manifestkonstanten gebildet, die in \<fcntl.h> definiert sind. Wenn mindestens zwei Konstanten das Argument `oflag` bilden, werden sie mit dem bitweisen OR-Operator (`|`) kombiniert.  
  
 `_O_APPEND`  
 Positioniert einen Dateizeiger vor jedem Schreibvorgang am Ende einer Datei.  
  
 `_O_BINARY`  
 Öffnet eine Datei im binären (unübersetzten) Modus. (Eine Beschreibung des binären Modus finden Sie unter [fopen](../../c-runtime-library/reference/fopen-wfopen.md).)  
  
 `_O_CREAT`  
 Erstellt eine Datei und öffnet sie zum Schreiben. Hat keine Auswirkung, wenn die von `filename` angegebene Datei vorhanden ist.  
  
 `_O_CREAT | _O_SHORT_LIVED`  
 Erstellt eine Datei als temporär und schreibt sie, wenn möglich, nicht auf den Datenträger.  
  
 `_O_CREAT | _O_TEMPORARY`  
 Erstellt eine Datei als temporär. Die Datei wird gelöscht, wenn der letzte Dateideskriptor geschlossen wird.  
  
 `_O_CREAT | _O_EXCL`  
 Gibt einen Fehlerwert zurück, wenn die von `filename` angegebene Datei vorhanden ist. Gilt nur bei Verwendung mit `_O_CREAT`.  
  
 `_O_NOINHERIT`  
 Verhindert die Erstellung eines freigegebenen Dateideskriptors.  
  
 `_O_RANDOM`  
 Legt primär den direkten Zugriff von der Festplatte fest.  
  
 `_O_RDONLY`  
 Öffnet eine Datei nur zum Lesen. Kann nicht mit `_O_RDWR` oder `_O_WRONLY` angegeben werden.  
  
 `_O_RDWR`  
 Öffnet eine Datei zum Lesen und zum Schreiben. Kann nicht mit `_O_RDONLY` oder `_O_WRONLY` angegeben werden.  
  
 `_O_SEQUENTIAL`  
 Legt primär den sequenziellen Zugriff von der Festplatte fest.  
  
 `_O_TEXT`  
 Öffnet eine Datei im Textmodus (übersetzt). (Weitere Informationen finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [fopen](../../c-runtime-library/reference/fopen-wfopen.md).)  
  
 `_O_TRUNC`  
 Öffnet eine Datei und verkürzt sie auf die Länge Null. Für die Datei muss Schreibberechtigung bestehen. Kann nicht mit `_O_RDONLY` angegeben werden. `_O_TRUNC` in Kombination mit `_O_CREAT` öffnet eine existierende Datei oder erstellt eine Datei.  
  
> [!NOTE]
>  Das Flag `_O_TRUNC` zerstört den Inhalt der angegebenen Datei.  
  
 `_O_WRONLY`  
 Öffnet eine Datei nur zum Schreiben. Kann nicht mit `_O_RDONLY` oder `_O_RDWR` angegeben werden.  
  
 `_O_U16TEXT`  
 Öffnet eine Datei im Unicode-UTF-16-Modus.  
  
 `_O_U8TEXT`  
 Öffnet eine Datei im Unicode-UTF-8-Modus.  
  
 `_O_WTEXT`  
 Öffnet eine Datei im Unicode-Modus.  
  
 Um den Datenzugriffsmodus festzulegen, müssen Sie entweder `_O_RDONLY`, `_O_RDWR` oder `_O_WRONLY` festlegen. Es existiert kein Standardwert für den Zugriffsmodus.  
  
 Wenn eine Datei mit `_O_WTEXT`, `_O_U8TEXT` oder `_O_U16TEXT` im Unicode-Modus geöffnet wird, übersetzen die Eingabefunktionen die aus der Datei gelesenen Daten in UTF-16-Daten, die als Datentyp `wchar_t` gespeichert werden. Funktionen, die in eine im Unicode-Modus geöffnete Datei schreiben, erwarten Puffer, die UTF-16-Daten, die als Datentyp `wchar_t` gespeichert sind. Wenn eine Datei als UTF-8 kodiert ist, dann werden UTF-16-Daten beim Schreiben in UTF-8 übersetzt, und die UTF-8-kodierten Inhalte der Datei werden beim Lesen in UTF-16 übersetzt. Der Versuch, in diesem Modus eine ungerade Anzahl von Bytes in Unicode zu lesen oder zu schreiben, führt zu einem Parametervalidierungsfehler. Wenn Sie Daten lesen oder schreiben möchten, die in Ihrem Programm als UTF-8 gespeichert sind, verwenden Sie den Text- oder Binärdateienmodus anstelle eines Unicode-Modus. Sie sind für jede erforderliche Kodierungsübersetzung verantwortlich.  
  
 Wenn `_sopen_s` mit `_O_WRONLY | _O_APPEND` (Anfügemodus) und `_O_WTEXT`,`_O_U16TEXT` oder `_O_U8TEXT` aufgerufen wird, versucht sie zuerst, die Datei zum Lesen und Schreiben zu öffnen, und dann, die BOM zu lesen und die Datei erneut, jedoch nur zum Schreiben, zu öffnen. Wenn das Öffnen der Datei zum Lesen und Schreiben fehlschlägt, wird die Datei nur zum Schreiben geöffnet und der Standardwert für die Unicode-Moduseinstellung verwendet.  
  
 Das Argument `shflag` ist ein Konstantenausdruck, der aus einer der folgenden Manifestkonstanten besteht, die in \<share.h> definiert sind.  
  
 `_SH_DENYRW`  
 Verweigert den Lese- und Schreibzugriff auf eine Datei.  
  
 `_SH_DENYWR`  
 Verweigert den Schreibzugriff auf eine Datei.  
  
 `_SH_DENYRD`  
 Verweigert den Lesezugriff auf eine Datei.  
  
 `_SH_DENYNO`  
 Gestattet Lese- und Schreibzugriff.  
  
 Das Argument `pmode` ist immer erforderlich, im Gegensatz zu `_sopen`. Wenn Sie `_O_CREAT` angeben und die Datei nicht vorhanden ist, gibt `pmode` die Berechtigungseinstellungen der Datei an, die festgelegt werden, wenn die neue Datei zum ersten Mal geschlossen wird. Andernfalls wird `pmode` ignoriert. `pmode` ist ein ganzzahliger Ausdruck, der eine oder beide der Manifestkonstanten `_S_IWRITE` und `_S_IREAD` enthält, die in \<sys\stat.h> definiert sind. Wenn beide Konstanten verwendet werden, werden sie mithilfe des bitweisen OR-Operators kombiniert. 
          `pmode` hat folgende Bedeutung:  
  
 `_S_IWRITE`  
 Schreiben erlaubt.  
  
 `_S_IREAD`  
 Lesen erlaubt.  
  
 `_S_IREAD | _S_IWRITE`  
 Lesen und Schreiben erlaubt.  
  
 Wenn keine Schreibberechtigung gewährt wird, kann die Datei nur gelesen werden. Im Windows-Betriebssystem sind alle Dateien lesbar. Es ist nicht möglich, nur Schreibberechtigungen zu vergeben. Deshalb sind die Modi `_S_IWRITE` und `_S_IREAD | _S_IWRITE` gleichwertig.  
  
 `_sopen_s` wendet die aktuelle Dateiberechtigungsmaske für `pmode` an, bevor die Berechtigungen festgelegt werden. (Siehe [_umask](../../c-runtime-library/reference/umask.md).)  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_sopen_s`|\<io.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>, \<share.h>|  
|`_wsopen_s`|\<io.h> oder \<wchar.h>|\<fcntl.h>, \<sys/types.h>, \<sys/stat.h>, \<share.h>|  
  
 `_sopen_s` und `_wsopen_s` sind Microsoft-Erweiterungen. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [_locking](../../c-runtime-library/reference/locking.md).  
  
## <a name="see-also"></a>Siehe auch  
 [E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [_schließen](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_fsopen, _wfsopen](../../c-runtime-library/reference/fsopen-wfsopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)