---
title: _open, _wopen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _open
- _wopen
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
- _wopen
- _topen
- _open
dev_langs:
- C++
helpviewer_keywords:
- opening files, for file I/O
- topen function
- _open function
- _topen function
- _wopen function
- files [C++], opening
- wopen function
- open function
ms.assetid: 13f6a0c3-d1aa-450d-a7aa-74abc91b163e
caps.latest.revision: 31
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
ms.openlocfilehash: 82b12ebfbff06c19a863bec7d8be2e6677c0148e
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="open-wopen"></a>_open, _wopen
Öffnet eine Datei. Diese Funktionen sind veraltet, da sichere Versionen verfügbar sind; siehe [_sopen_s, _wsopen_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _open(  
   const char *filename,  
   int oflag [,  
   int pmode]   
);  
int _wopen(  
   const wchar_t *filename,  
   int oflag [,  
   int pmode]   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Dateiname  
  
 `oflag`  
 Die Art der zulässigen Vorgänge.  
  
 `pmode`  
 Berechtigungsmodus.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt einen Dateideskriptor für die geöffnete Datei zurück. Der Rückgabewert -1 weist auf einen Fehler hin. In diesem Fall wird `errno` auf einen der folgenden Werte festgelegt.  
  
 `EACCES`  
 Versuch, eine schreibgeschützte Datei zum Schreiben zu öffnen, der Freigabemodus der Datei lässt die angegebenen Vorgänge nicht zu, oder der vorgegebene Pfad ist ein Verzeichnis.  
  
 `EEXIST`  
 `_O_CREAT`- und `_O_EXCL`-Flag angegeben, aber `filename` ist bereits vorhanden.  
  
 `EINVAL`  
 Ungültiges `oflag`- oder `pmode`-Argument.  
  
 `EMFILE`  
 Es sind keine weiteren Dateideskriptoren verfügbar (zu viele Dateien sind geöffnet).  
  
 `ENOENT`  
 Datei oder Pfad nicht gefunden.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_open` öffnet die von `filename` angegebene Datei und bereitet sie für das Lesen oder Schreiben vor, wie von `oflag` angegeben. `_wopen` ist eine Breitzeichenversion von `_open`. Das `filename`-Argument für `_wopen` ist eine Breitzeichenfolge. `_wopen` und `_open` verhalten sich andernfalls identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_topen`|`_open`|`_open`|`_wopen`|  
  
 `oflag` ist ein Ganzzahlausdruck, der von einer oder mehreren der folgenden Manifestkonstanten oder Konstantenkombinationen gebildet wurde, die in \<fcntl.h> definiert sind.  
  
 `_O_APPEND`  
 Verschiebt den Dateizeiger vor jedem Schreibvorgang an das Ende der Datei.  
  
 `_O_BINARY`  
 Öffnet die Datei im Binärmodus (nicht übersetzt). (Eine Beschreibung des binären Modus finden Sie unter [fopen](../../c-runtime-library/reference/fopen-wfopen.md).)  
  
 `_O_CREAT`  
 Erstellt eine Datei und öffnet sie zum Schreiben. Hat keine Auswirkung, wenn die durch `filename` angegebene Datei existiert. Das Argument `pmode` ist erforderlich, wenn `_O_CREAT` angegeben wird.  
  
 `_O_CREAT` &#124; `_O_SHORT_LIVED`  
 Erstellt eine temporäre Datei und leert sie, wenn möglich, nicht auf die Festplatte. Das Argument `pmode` ist erforderlich, wenn `_O_CREAT` angegeben wird.  
  
 `_O_CREAT` &#124; `_O_TEMPORARY`  
 Erstellt eine temporäre Datei. Die Datei wird gelöscht, wenn der letzte Dateideskriptor geschlossen wird. Das Argument `pmode` ist erforderlich, wenn `_O_CREAT` angegeben wird.  
  
 `_O_CREAT` &#124; `_O_EXCL`  
 Gibt einen Fehlerwert zurück, wenn die von `filename` angegebene Datei vorhanden ist. Gilt nur bei Verwendung mit `_O_CREAT`.  
  
 `_O_NOINHERIT`  
 Verhindert die Erstellung eines gemeinsam verwendeten Dateideskriptors.  
  
 `_O_RANDOM`  
 Gibt an, dass das Zwischenspeichern für den zufälligen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.  
  
 `_O_RDONLY`  
 Öffnet eine Datei nur zum Lesen. Kann nicht mit `_O_RDWR` oder `_O_WRONLY` angegeben werden.  
  
 `_O_RDWR`  
 Öffnet eine Datei sowohl zum Lesen als auch zum Schreiben. Kann nicht mit `_O_RDONLY` oder `_O_WRONLY` angegeben werden.  
  
 `_O_SEQUENTIAL`  
 Gibt an, dass das Zwischenspeichern für den sequenziellen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.  
  
 `_O_TEXT`  
 Öffnet eine Datei im Textmodus (übersetzt). (Weitere Informationen finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [fopen](../../c-runtime-library/reference/fopen-wfopen.md).)  
  
 `_O_TRUNC`  
 Öffnet eine Datei und verkürzt sie auf die Länge Null. Für die Datei muss Schreibberechtigung bestehen. Kann nicht mit `_O_RDONLY` angegeben werden. `_O_TRUNC` in Kombination mit `_O_CREAT` öffnet eine existierende Datei oder erstellt eine Datei.  
  
> [!NOTE]
>  Das `_O_TRUNC`-Flag zerstört die Inhalte der angegebenen Datei.  
  
 `_O_WRONLY`  
 Öffnet die Datei nur zum Schreiben. Kann nicht mit `_O_RDONLY` oder `_O_RDWR` angegeben werden.  
  
 `_O_U16TEXT`  
 Öffnet die Datei im Unicode UTF-16-Modus.  
  
 `_O_U8TEXT`  
 Öffnet die Datei im Unicode UTF-8-Modus.  
  
 `_O_WTEXT`  
 Öffnet die Datei im Unicode-Modus.  
  
 Zum Angeben des Dateizugriffsmodus müssen Sie `_O_RDONLY`, `_O_RDWR` oder `_O_WRONLY` angeben. Es gibt keinen Standardwert für den Zugriffsmodus.  
  
 Wenn `_O_WTEXT` verwendet wird, um eine Datei zum Lesen zu öffnen, liest `_open` den Anfang der Datei und überprüft sie auf eine Bytereihenfolgemarkierung (BOM). Wenn eine BOM vorhanden ist, wird die Datei je nach BOM als UTF-8 oder UTF-16LE behandelt. Wenn keine BOM vorhanden ist, wird die Datei als ANSI behandelt. Wenn eine Datei mit `_O_WTEXT` zum Schreiben geöffnet wird, wird UTF-16 verwendet. Unabhängig von früheren Einstellungen oder Bytereihenfolgemarkierungen wird die Datei bei Verwendung von `_O_U8TEXT` immer als UTF-8 geöffnet. Wenn `_O_U16TEXT` verwendet wird, wird die Datei immer als UTF-16 geöffnet.  
  
 Wenn eine Datei mit `_O_WTEXT`, `_O_U8TEXT` oder `_O_U16TEXT` im Unicode-Modus geöffnet wird, übersetzen Eingabefunktionen die Daten, die aus der Datei gelesen werden, in UTF-16-Daten, die als Typ `wchar_t` gespeichert werden. Funktionen, die in eine im Unicode-Modus geöffnete Datei schreiben, erwarten Puffer, die UTF-16-Daten, die als Datentyp `wchar_t` gespeichert sind. Wenn eine Datei als UTF-8 kodiert ist, dann werden UTF-16-Daten beim Schreiben in UTF-8 übersetzt, und die UTF-8-kodierten Inhalte der Datei werden beim Lesen in UTF-16 übersetzt. Der Versuch, in diesem Modus eine ungerade Anzahl von Bytes in Unicode zu lesen oder zu schreiben, führt zu einem Parametervalidierungsfehler. Wenn Sie Daten lesen oder schreiben möchten, die in Ihrem Programm als UTF-8 gespeichert sind, verwenden Sie den Text- oder Binärdateienmodus anstelle eines Unicode-Modus. Sie sind für jede erforderliche Kodierungsübersetzung verantwortlich.  
  
 Wenn `_open` mit `_O_WRONLY|_O_APPEND` (Anfügemodus) und `_O_WTEXT`,`_O_U16TEXT` oder `_O_U8TEXT` aufgerufen wird, versucht sie zuerst, die Datei zum Lesen und Schreiben zu öffnen, und dann, die BOM zu lesen und die Datei erneut, jedoch nur zum Schreiben, zu öffnen. Wenn das Öffnen der Datei zum Lesen und Schreiben fehlschlägt, wird die Datei nur zum Schreiben geöffnet und der Standardwert für die Unicode-Moduseinstellung verwendet.  
  
 Wenn zwei oder mehr Manifestkonstanten verwendet werden, um das `oflag`-Argument zu bilden, werden die Konstanten mit dem bitweisen OR-Operator kombiniert ( `|` ). Eine Darstellung des Binär- und Textmodus finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
 Das Argument `pmode` ist nur erforderlich, wenn `_O_CREAT` angegeben ist. Wenn die Datei bereits vorhanden ist, wird `pmode` ignoriert. Andernfalls gibt `pmode` die Dateiberechtigungseinstellungen an, die festgelegt werden, wenn die neue Datei zum ersten Mal geschlossen wird. `_open` wendet die aktuelle Dateiberechtigungsmaske für `pmode` an, bevor die Berechtigungen festgelegt werden. (Weitere Informationen finden Sie unter [_umask](../../c-runtime-library/reference/umask.md)). `pmode` ist ein Ganzzahlausdruck, der eine oder beide der folgenden Manifestkonstanten enthält, die in \<sys\stat.h> definiert sind.  
  
 `_S_IREAD`  
 Nur Lesen zugelassen.  
  
 `_S_IWRITE`  
 Schreiben zugelassen. (Lässt tatsächlich Lesen und Schreiben zu.)  
  
 `_S_IREAD`  `|`  `_S_IWRITE`  
 Lesen und Schreiben erlaubt.  
  
 Wenn beide Konstanten gegeben sind, werden sie mit dem bitweisen OR-Operator verbunden ( `|` ). In Windows sind alle Dateien lesbar, eine schreibgeschützte Berechtigung ist nicht verfügbar. Deshalb sind die Modi `_S_IWRITE` und `_S_IREAD` `|` `_S_IWRITE` gleichwertig.  
  
 Wenn ein anderer Wert als eine Kombination aus `_S_IREAD` und `_S_IWRITE` für `pmode` angegeben wird – selbst wenn dieser einen gültigen `pmode` in einem anderen Betriebssystem angeben würde – oder wenn ein anderer Wert als die zulässigen `oflag`-Werte angegeben wird, generiert die Funktion eine Assertion im Debugmodus und ruft den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion -1 zurück und stellt `errno` auf `EINVAL`ein.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_open`|\<io.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>|  
|`_wopen`|\<io.h> oder \<wchar.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>|  
  
 `_open` und `_wopen` sind Microsoft-Erweiterungen. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_open.c  
// compile with: /W3  
/* This program uses _open to open a file  
 * named CRT_OPEN.C for input and a file named CRT_OPEN.OUT  
 * for output. The files are then closed.  
 */  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int fh1, fh2;  
  
   fh1 = _open( "CRT_OPEN.C", _O_RDONLY ); // C4996  
   // Note: _open is deprecated; consider using _sopen_s instead  
   if( fh1 == -1 )  
      perror( "Open failed on input file" );  
   else  
   {  
      printf( "Open succeeded on input file\n" );  
      _close( fh1 );  
   }  
  
   fh2 = _open( "CRT_OPEN.OUT", _O_WRONLY | _O_CREAT, _S_IREAD |   
                            _S_IWRITE ); // C4996  
   if( fh2 == -1 )  
      perror( "Open failed on output file" );  
   else  
   {  
      printf( "Open succeeded on output file\n" );  
      _close( fh2 );  
   }  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
Open succeeded on input file  
Open succeeded on output file  
```  
  
## <a name="see-also"></a>Siehe auch  
 [E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_schließen](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)
