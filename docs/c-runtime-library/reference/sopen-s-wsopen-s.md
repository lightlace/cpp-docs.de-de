---
title: "_sopen_s, _wsopen_s"
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
  - "_sopen_s"
  - "_wsopen_s"
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
  - "_sopen_s"
  - "wsopen_s"
  - "_wsopen_s"
  - "sopen_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_sopen_s-Funktion"
  - "_wsopen_s-Funktion"
  - "Dateien [C++], Öffnen"
  - "Dateien [C++], Freigeben"
  - "Öffnen von Dateien, für die Freigabe"
  - "sopen_s-Funktion"
  - "wsopen_s-Funktion"
ms.assetid: 059a0084-d08c-4973-9174-55e391b72aa2
caps.latest.revision: 29
caps.handback.revision: "29"
ms.author: "corob"
manager: "ghogen"
---
# _sopen_s, _wsopen_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Öffnet eine Datei zum Freigeben.  Bei diesen Versionen von [\_sopen and \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md) wurde die Sicherheit wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben verbessert.  
  
## Syntax  
  
```  
errno_t _sopen_s(    int* pfh,    const char *filename,    int oflag,    int shflag,    int pmode ); errno_t _wsopen_s(    int* pfh,    const wchar_t *filename,    int oflag,    int shflag,    int pmode, );  
```  
  
#### Parameter  
 \[out\] `pfh`  
 Das Dateihandle oder \-1 im Fall eines Fehlers.  
  
 \[in\] `filename`  
 Dateiname  
  
 \[in\] `oflag`  
 Die Art der zulässigen Vorgänge.  
  
 \[in\] `shflag`  
 Die Art der zulässigen Freigabe.  
  
 \[in\] `pmode`  
 Berechtigungseinstellung.  
  
## Rückgabewert  
 Ein Rückgabewert ungleich Null weist auf einen Fehler hin. In diesem Fall wird `errno` auf einen der folgenden Werte festgelegt.  
  
 `EACCES`  
 Der angegebene Pfad ist ein Verzeichnis, oder die Datei ist schreibgeschützt, aber es wurde versucht, einen Vorgang für das Öffnen zum Schreiben durchzuführen.  
  
 `EEXIST`  
 `_O_CREAT`\- und `_O_EXCL`\-Flag wurden angegeben, aber `filename` ist bereits vorhanden.  
  
 `EINVAL`  
 Ungültiges `oflag`\-, `shflag`\- oder `pmode`\-Argument, oder `pfh` oder `filename` war ein NULL\-Zeiger.  
  
 `EMFILE`  
 Es sind keine Dateideskriptoren mehr verfügbar.  
  
 `ENOENT`  
 Datei oder Pfad nicht gefunden.  
  
 Wenn ein ungültiges Argument an die Funktion übergeben wird, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` festgelegt und `EINVAL` zurückgegeben.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Im Fall eines Fehlers wird \-1 über `pfh` zurückgegeben \(es sein denn, `pfh` ist ein NULL\-Zeiger\).  
  
## Hinweise  
 Die Funktion `_sopen_s` öffnet die von `filename` angegebene Datei und bereitet die Datei für freigegebenes Lesen oder Schreiben vor, wie von `oflag` und `shflag` definiert.  `_wsopen_s` ist eine Breitzeichenversion von `_sopen_s`. Das `filename`\-Argument für `_wsopen_s` ist eine Breitzeichenfolge.  `_wsopen_s` und `_sopen_s` verhalten sich andernfalls identisch.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tsopen_s`|`_sopen_s`|`_sopen_s`|`_wsopen_s`|  
  
 Der Ganzzahlausdruck `oflag` wird durch das Kombinieren einer oder mehrerer Manifestkonstanten gebildet, die in \<fcntl.h\> definiert sind.  Wenn zwei oder mehr Konstanten das Argument `oflag` bilden, werden sie mit dem bitweisen OR\-Operator kombiniert \(  `|` \).  
  
 `_O_APPEND`  
 Positioniert den Dateizeiger vor jedem Schreibvorgang an das Ende der Datei neu.  
  
 `_O_BINARY`  
 Öffnet eine Datei im Binärmodus \(nicht übersetzt\).  \(Eine Beschreibung des Binärmodus finden Sie unter [fopen](../../c-runtime-library/reference/fopen-wfopen.md).\)  
  
 `_O_CREAT`  
 Erstellt eine Datei und öffnet sie zum Schreiben.  Hat keine Auswirkung, wenn die von `filename` angegebene Datei vorhanden ist.  
  
 `_O_CREAT | _O_SHORT_LIVED`  
 Erstellt eine Datei als temporär und schreibt sie, wenn möglich, nicht auf den Datenträger.  
  
 `_O_CREAT | _O_TEMPORARY`  
 Erstellt eine Datei als temporär. Die Datei wird gelöscht, wenn der letzte Dateideskriptor geschlossen wird.  
  
 `_O_CREAT | _O_EXCL`  
 Gibt einen Fehlerwert zurück, wenn die von `filename` angegebene Datei vorhanden ist.  Gilt nur bei Verwendung mit `_O_CREAT`.  
  
 `_O_NOINHERIT`  
 Verhindert die Erstellung eines gemeinsam verwendeten Dateideskriptors.  
  
 `_O_RANDOM`  
 Gibt primär einen zufälligen Zugriff vom Datenträger an.  
  
 `_O_RDONLY`  
 Öffnet eine Datei nur zum Lesen.  Kann nicht mit `_O_RDWR` oder `_O_WRONLY` angegeben werden.  
  
 `_O_RDWR`  
 Öffnet eine Datei sowohl zum Lesen als auch zum Schreiben.  Kann nicht mit `_O_RDONLY` oder `_O_WRONLY` angegeben werden.  
  
 `_O_SEQUENTIAL`  
 Gibt primär den sequenziellen Zugriff vom Datenträger an.  
  
 `_O_TEXT`  
 Öffnet eine Datei im Textmodus \(übersetzt\).  \(Weitere Informationen finden Sie unter [Text\- und Binärmodus\-Datei\-E\/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [fopen](../../c-runtime-library/reference/fopen-wfopen.md).\)  
  
 `_O_TRUNC`  
 Öffnet eine Datei und kürzt sie auf eine Länge von Null. Die Datei muss über eine Schreibberechtigung verfügen.  Kann nicht mit `_O_RDONLY` angegeben werden.  `_O_TRUNC` öffnet bei Verwendung mit `_O_CREAT` eine vorhandene Datei oder erstellt eine Datei.  
  
> [!NOTE]
>  Das `_O_TRUNC`\-Flag zerstört die Inhalte der angegebenen Datei.  
  
 `_O_WRONLY`  
 Öffnet eine Datei nur zum Schreiben.  Kann nicht mit `_O_RDONLY` oder `_O_RDWR` angegeben werden.  
  
 `_O_U16TEXT`  
 Öffnet eine Datei im Unicode UTF\-16\-Modus.  
  
 `_O_U8TEXT`  
 Öffnet eine Datei im Unicode UTF\-8\-Modus.  
  
 `_O_WTEXT`  
 Öffnet eine Datei im Unicode\-Modus.  
  
 Zum Angeben des Dateizugriffsmodus müssen Sie `_O_RDONLY`, `_O_RDWR` oder `_O_WRONLY` angeben.  Es gibt keinen Standardwert für den Zugriffsmodus.  
  
 Wenn eine Datei mit `_O_WTEXT`, `_O_U8TEXT` oder `_O_U16TEXT` im Unicode\-Modus geöffnet wird, übersetzen Eingabefunktionen die Daten, die aus der Datei gelesen werden, in UTF\-16\-Daten, die als Typ `wchar_t` gespeichert werden.  Funktionen, die an eine im Unicode\-Modus geöffnete Datei schreiben, erwarten Puffer, die UTF\-16\-Daten enthalten, die als Typ `wchar_t` gespeichert sind.  Wenn die Datei als UTF\-8 codiert ist, werden UTF\-16\-Daten beim Schreiben in UTF\-8 übersetzt, und die UTF\-8\-codierten Inhalte der Datei werden beim Lesen in UTF\-16 übersetzt.  Der Versuch, eine ungerade Anzahl von Bytes im Unicode\-Modus zu lesen oder zu schreiben, verursacht einen Parametervalidierungsfehler.  Verwenden Sie zum Lesen oder Schreiben von Daten, die als UTF\-8 in Ihrem Programm gespeichert sind, einen Text\- oder Binärdateimodus anstelle eines Unicode\-Modus.  Sie sind für die gesamte erforderliche Codierungsübersetzung verantwortlich.  
  
 Wenn `_sopen_s` mit `_O_WRONLY | _O_APPEND` \(Append\-Modus\) und `_O_WTEXT`, `_O_U16TEXT` oder `_O_U8TEXT` aufgerufen wird, wird zuerst versucht, die Datei zum Lesen und Schreiben zu öffnen, die BOM zu lesen und sie dann nur zum Schreiben zu öffnen.  Wenn das Öffnen der Datei zum Lesen und Schreiben fehlschlägt, wird die Datei nur zum Schreiben geöffnet und der Standardwert für die Unicode\-Moduseinstellung verwendet.  
  
 Das Argument `shflag` ist ein Konstantenausdruck, der aus einer der folgenden Manifestkonstanten besteht, die in \<share.h\> definiert sind.  
  
 `_SH_DENYRW`  
 Verweigerte Lese\- und Schreibzugriff auf eine Datei.  
  
 `_SH_DENYWR`  
 Verweigert Schreibzugriff auf eine Datei.  
  
 `_SH_DENYRD`  
 Verweigert Lesezugriff auf eine Datei.  
  
 `_SH_DENYNO`  
 Gestattet Lese\- und Schreibzugriff.  
  
 Das Argument `pmode` ist immer erforderlich, im Gegensatz zu `_sopen`.  Wenn Sie `_O_CREAT` angeben und die Datei nicht vorhanden ist, gibt `pmode` die Berechtigungseinstellungen der Datei an, die festgelegt werden, wenn die neue Datei zum ersten Mal geschlossen wird.  Andernfalls wird `pmode` ignoriert.  `pmode` ist ein Ganzzahlausdruck, der eine oder beide der Manifestkonstanten `_S_IWRITE` und `_S_IREAD` enthält, die in \<sys\\stat.h\> definiert sind.  Wenn beide Konstanten angegeben sind, werden sie mit dem bitweisen OR\-Operator kombiniert.  Die Bedeutung von `pmode` lautet wie folgt:  
  
 `_S_IWRITE`  
 Schreiben zugelassen.  
  
 `_S_IREAD`  
 Lesen zugelassen.  
  
 `_S_IREAD | _S_IWRITE`  
 Lesen und Schreiben zugelassen.  
  
 Wenn die Schreibberechtigung nicht gegeben ist, ist die Datei schreibgeschützt.  Im Windows\-Betriebssystem sind alle Dateien lesbar. Es ist nicht möglich, eine schreibgeschützte Berechtigung zu erteilen.  Daher sind die Modi `_S_IWRITE` und `_S_IREAD | _S_IWRITE` gleich.  
  
 `_sopen_s` wendet die aktuelle Dateiberechtigungsmaske für `pmode` an, bevor die Berechtigungen festgelegt werden.  \(Siehe [\_umask](../../c-runtime-library/reference/umask.md).\)  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_sopen_s`|\<io.h\>|\<fcntl.h\>, \<sys\\types.h\>, \<sys\\stat.h\>, \<share.h\>|  
|`_wsopen_s`|\<io.h\> oder \<wchar.h\>|\<fcntl.h\>, \<sys\/types.h\>, \<sys\/stat.h\>, \<share.h\>|  
  
 `_sopen_s` und `_wsopen_s` sind Microsoft\-Erweiterungen.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Ein Beispiel hierfür finden Sie unter [\_locking](../../c-runtime-library/reference/locking.md).  
  
## Siehe auch  
 [E\/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_fsopen, \_wfsopen](../../c-runtime-library/reference/fsopen-wfsopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)