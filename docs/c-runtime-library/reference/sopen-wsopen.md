---
title: _sopen, _wsopen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _sopen
- _wsopen
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
- _wsopen
- wsopen
- _sopen
- _tsopen
dev_langs:
- C++
helpviewer_keywords:
- sopen function
- sharing files
- opening files, for sharing
- _sopen function
- wsopen function
- files [C++], opening
- files [C++], sharing
- _wsopen function
ms.assetid: a9d4cccf-06e9-414d-96fa-453fca88cc1f
caps.latest.revision: 21
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
ms.openlocfilehash: aac10cebd0f967944403837283e9008b0b1047fc
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="sopen-wsopen"></a>_sopen, _wsopen
Öffnet eine Datei zur Freigabe. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_sopen_s, _wsopen_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _sopen(  
   const char *filename,  
   int oflag,  
   int shflag [,  
   int pmode ]   
);  
int _wsopen(  
   const wchar_t *filename,  
   int oflag,  
   int shflag [,  
   int pmode ]   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Dateiname  
  
 `oflag`  
 Die zulässige Art von Vorgängen.  
  
 `shflag`  
 Die zulässige Freigabeart.  
  
 `pmode`  
 Berechtigungseinstellung.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt einen Dateideskriptor für die geöffnete Datei zurück.  
  
 Wenn `filename` oder `oflag` ein `NULL`-Zeiger ist oder wenn `oflag` oder `shflag` nicht innerhalb eines gültigen Bereichs von Werten liegt, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen –1 zurück und setzen `errno` auf einen der folgenden Werte.  
  
 `EACCES`  
 Der angegebene Pfad ist ein Verzeichnis, oder die Datei ist schreibgeschützt, aber es wurde versucht, sie zum Schreiben zu öffnen.  
  
 `EEXIST`  
Die Flags  `_O_CREAT` und `_O_EXCL` wurden angegeben, `filename` existiert jedoch bereits.  
  
 `EINVAL`  
 Ungültiges `oflag`- oder `shflag`-Argument.  
  
 `EMFILE`  
 Es sind keine Dateideskriptoren mehr verfügbar.  
  
 `ENOENT`  
 Datei oder Pfad nicht gefunden.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_sopen` öffnet die durch `filename` angegebene Datei und bereitet sie zur Lese- oder Schreibfreigabe vor, wie in `oflag` und `shflag` definiert. `_wsopen` ist eine Breitzeichenversion von `_sopen`. Das `filename`-Argument für `_wsopen` ist eine Breitzeichenfolge. `_wsopen` und `_sopen` verhalten sich andernfalls identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsopen`|`_sopen`|`_sopen`|`_wsopen`|  
  
 Der ganzzahlige Ausdruck `oflag` wird durch Kombination einer oder mehrerer der folgenden Manifestkonstanten gebildet, die in \<fcntl.h> definiert werden. Wenn mindestens zwei Konstanten das Argument `oflag` bilden, werden sie mit dem bitweisen OR-Operator (`|`) kombiniert.  
  
 `_O_APPEND`  
 Positioniert einen Dateizeiger vor jedem Schreibvorgang am Ende einer Datei.  
  
 `_O_BINARY`  
 Öffnet eine Datei im binären (unübersetzten) Modus. (Eine Beschreibung des binären Modus finden Sie unter [fopen](../../c-runtime-library/reference/fopen-wfopen.md).)  
  
 `_O_CREAT`  
 Erstellt eine Datei und öffnet sie zum Schreiben. Hat keine Auswirkung, wenn die durch `filename` angegebene Datei existiert. Das Argument `pmode` ist erforderlich, wenn `_O_CREAT` angegeben wird.  
  
 `_O_CREAT | _O_SHORT_LIVED`  
 Erstellt eine temporäre Datei und leert sie, wenn möglich, nicht auf die Festplatte. Das Argument `pmode` ist erforderlich, wenn `_O_CREAT` angegeben wird.  
  
 `_O_CREAT | _O_TEMPORARY`  
 Erstellt eine temporäre Datei. Die Datei wird gelöscht, wenn der letzte Dateideskriptor geschlossen wird. Das Argument `pmode` ist erforderlich, wenn `_O_CREAT` angegeben wird.  
  
 `_O_CREAT | _O_EXCL`  
 Gibt einen Fehlerwert zurück, wenn eine durch `filename` angegebene Datei existiert. Gilt nur in Verwendung mit `_O_CREAT`.  
  
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
  
 Wenn `_sopen` mit `_O_WRONLY | _O_APPEND` (Anfügemodus) und `_O_WTEXT`,`_O_U16TEXT` oder `_O_U8TEXT` aufgerufen wird, versucht sie zuerst, die Datei zum Lesen und Schreiben zu öffnen, und dann, die BOM zu lesen und die Datei erneut, jedoch nur zum Schreiben, zu öffnen. Wenn das Öffnen der Datei zum Lesen und Schreiben fehlschlägt, wird die Datei nur zum Schreiben geöffnet und der Standardwert für die Unicode-Moduseinstellung verwendet.  
  
 Das Argument `shflag` ist ein konstanter Ausdruck, der aus einer der folgenden Manifestkonstanten besteht, die in \<share.h> definiert sind.  
  
 `_SH_DENYRW`  
 Verweigert den Lese- und Schreibzugriff auf eine Datei.  
  
 `_SH_DENYWR`  
 Verweigert den Schreibzugriff auf eine Datei.  
  
 `_SH_DENYRD`  
 Verweigert den Lesezugriff auf eine Datei.  
  
 `_SH_DENYNO`  
 Erlaubt Lese- und Schreibzugriff.  
  
 Das Argument `pmode` ist nur erforderlich, wenn `_O_CREAT` angegeben wird. Wenn die Datei nicht existiert, gibt `pmode` die Berechtigungseinstellungen der Datei an, die festgelegt werden, wenn die neue Datei zum ersten Mal geschlossen wird. Andernfalls wird `pmode` ignoriert. `pmode` ist ein ganzzahliger Ausdruck, der eine oder beide der Manifestkonstanten `_S_IWRITE` und `_S_IREAD` enthält, die in \<sys\stat.h> definiert sind. Wenn beide Konstanten verwendet werden, werden sie mithilfe des bitweisen OR-Operators kombiniert. 
          `pmode` hat folgende Bedeutung:  
  
 `_S_IWRITE`  
 Schreiben erlaubt.  
  
 `_S_IREAD`  
 Lesen erlaubt.  
  
 `_S_IREAD | _S_IWRITE`  
 Lesen und Schreiben erlaubt.  
  
 Wenn keine Schreibberechtigung gewährt wird, kann die Datei nur gelesen werden. Im Windows-Betriebssystem sind alle Dateien lesbar. Es ist nicht möglich, nur Schreibberechtigungen zu vergeben. Deshalb sind die Modi `_S_IWRITE` und `_S_IREAD | _S_IWRITE` gleichwertig.  
  
 `_sopen` wendet die aktuelle Dateiberechtigungsmaske für `pmode` an, bevor die Berechtigungen festgelegt werden. (Siehe [_umask](../../c-runtime-library/reference/umask.md).)  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_sopen`|\<io.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>, \<share.h>|  
|`_wsopen`|\<io.h> oder \<wchar.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>, \<share.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [_locking](../../c-runtime-library/reference/locking.md).  
  
## <a name="see-also"></a>Siehe auch  
 [E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_fsopen, _wfsopen](../../c-runtime-library/reference/fsopen-wfsopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
