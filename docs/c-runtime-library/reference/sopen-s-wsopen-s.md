---
title: _sopen_s, _wsopen_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- sopen_s function
- _wsopen_s function
- wsopen_s function
- opening files, for sharing
- files [C++], opening
- _sopen_s function
- files [C++], sharing
ms.assetid: 059a0084-d08c-4973-9174-55e391b72aa2
caps.latest.revision: 29
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf7e7261fe1883eee82945451bb4dbd2e3253814
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="sopens-wsopens"></a>_sopen_s, _wsopen_s

Öffnet eine Datei zur Freigabe. Diese Versionen von [_sopen und _wsopen](sopen-wsopen.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

## <a name="syntax"></a>Syntax

```C
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

### <a name="parameters"></a>Parameter

*PFH*<br/>
Das Dateihandle oder -1 im Fall eines Fehlers.

*filename*<br/>
Dateiname

*oflag*<br/>
Die zulässige Art von Vorgängen.

*shflag*<br/>
Die zulässige Freigabeart.

*pmode*<br/>
Berechtigungseinstellung.

## <a name="return-value"></a>Rückgabewert

Ein Rückgabewert ungleich Null gibt einen Fehler an. In diesem Fall **Errno** auf einen der folgenden Werte festgelegt.

|errno-Wert|Bedingung|
|-|-|
**EACCES**| Der angegebene Pfad ist ein Verzeichnis, oder die Datei ist schreibgeschützt, aber es wurde versucht, sie zum Schreiben zu öffnen.
**EEXIST**| **_O_CREAT** und **_O_EXCL** Kennzeichen wurden angegeben, aber *Filename* ist bereits vorhanden.
**EINVAL**| Ungültige *Oflag*, *Shflag*, oder *Pmode* Argument oder *Pfh* oder *Filename* wurde ein null-Zeiger.
**EMFILE**|Es sind keine Dateideskriptoren mehr verfügbar.
**ENOENT**|Datei oder Pfad nicht gefunden.

Wenn ein ungültiges Argument an die Funktion übergeben wird, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** festgelegt ist, um **EINVAL** und **EINVAL** wird zurückgegeben.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Im Falle eines Fehlers wird-1 zurückgegeben, durch *Pfh* (es sei denn, *Pfh* ist ein null-Zeiger).

## <a name="remarks"></a>Hinweise

Die **_sopen_s** -Funktion öffnet die Datei, die vom angegebenen *Filename* und die Datei für Lese- oder Schreibfreigabe, vorbereitet werden, gemäß der Definition von *Oflag* und *Shflag* . **_wsopen_s** ist eine Breitzeichen-Version von **_sopen_s**; das *Filename* Argument **_wsopen_s** ist eine Breitzeichen-Zeichenfolge. **_wsopen_s** und **_sopen_s** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsopen_s**|**_sopen_s**|**_sopen_s**|**_wsopen_s**|

Der Ganzzahlausdruck *Oflag* wird gebildet, indem das Kombinieren von mindestens Manifestkonstanten, die in definierten \<fcntl.h >. Wenn zwei oder mehr Konstanten das Argument bilden *Oflag*, sind mit dem bitweisen OR-Operator kombiniert ( **&#124;** ).

|*Oflag* Konstanten|Verhalten|
|-|-|
**_O_APPEND**|Verschiebt den Dateizeiger vor jedem Schreibvorgang an das Ende der Datei.
**_O_BINARY**|Öffnet die Datei im Binärmodus (nicht übersetzt). (Eine Beschreibung des binären Modus finden Sie unter [fopen](fopen-wfopen.md).)
**_O_CREAT**|Erstellt eine Datei und öffnet sie zum Schreiben. Hat keine Auswirkung, wenn die Datei durch angegeben *Filename* vorhanden ist. Die *Pmode* Argument ist erforderlich, wenn **_O_CREAT** angegeben ist.
**_O_CREAT** &AMP;#124; **_O_SHORT_LIVED**|Erstellt eine temporäre Datei und leert sie, wenn möglich, nicht auf die Festplatte. Die *Pmode* Argument ist erforderlich, wenn **_O_CREAT** angegeben ist.
**_O_CREAT** &AMP;#124; **_O_TEMPORARY**|Erstellt eine temporäre Datei. Die Datei wird gelöscht, wenn der letzte Dateideskriptor geschlossen wird. Die *Pmode* Argument ist erforderlich, wenn **_O_CREAT** angegeben ist.
**_O_CREAT**&AMP;#124; ` _O_EXCL`|Gibt einen Fehlerwert zurück, wenn eine Datei gemäß *Filename* vorhanden ist. Gilt nur bei Verwendung mit **_O_CREAT**.
**_O_NOINHERIT**|Verhindert die Erstellung eines gemeinsam verwendeten Dateideskriptors.
**_O_RANDOM**|Gibt an, dass das Zwischenspeichern für den zufälligen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.
**_O_RDONLY**|Öffnet eine Datei nur zum Lesen. Kann nicht angegeben werden, mit **_O_RDWR** oder **_O_WRONLY**.
**_O_RDWR**|Öffnet eine Datei zum Lesen und zum Schreiben. Kann nicht angegeben werden, mit **_O_RDONLY** oder **_O_WRONLY**.
**_O_SEQUENTIAL**|Gibt an, dass das Zwischenspeichern für den sequenziellen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.
**_O_TEXT**|Öffnet eine Datei im Textmodus (übersetzt). (Weitere Informationen finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [fopen](fopen-wfopen.md).)
**_O_TRUNC**|Öffnet eine Datei und verkürzt sie auf die Länge Null. Für die Datei muss Schreibberechtigung bestehen. Kann nicht angegeben werden, mit **_O_RDONLY**. **_O_TRUNC** mit verwendet **_O_CREAT** öffnet eine vorhandene Datei oder eine Datei erstellt. **Hinweis:** der **_O_TRUNC** Flag zerstört den Inhalt der angegebenen Datei.
**_O_WRONLY**|Öffnet eine Datei nur zum Schreiben. Kann nicht angegeben werden, mit **_O_RDONLY** oder **_O_RDWR**.
**_O_U16TEXT**|Öffnet eine Datei im Unicode-UTF-16-Modus.
**_O_U8TEXT**|Öffnet eine Datei im Unicode-UTF-8-Modus.
**_O_WTEXT**|Öffnet eine Datei im Unicode-Modus.

Um die Dateizugriffsmodus anzugeben, geben Sie **_O_RDONLY**, **_O_RDWR**, oder **_O_WRONLY**. Es gibt keinen Standardwert für den Zugriffsmodus.

Wenn eine Datei im Unicode-Modus mit geöffnet wird **_O_WTEXT**, **_O_U8TEXT**, oder **_O_U16TEXT**Eingabe übersetzen die Eingabefunktionen die aus der Datei Daten in UTF-16-Daten gelesenen gespeichert als Typ **Wchar_t**. Funktionen, die in eine im Unicode-Modus geöffnete Datei schreiben, erwarten Puffer, die UTF-16-Daten gespeichert, die als Typ enthalten **Wchar_t**. Wenn eine Datei als UTF-8 kodiert ist, dann werden UTF-16-Daten beim Schreiben in UTF-8 übersetzt, und die UTF-8-kodierten Inhalte der Datei werden beim Lesen in UTF-16 übersetzt. Der Versuch, in diesem Modus eine ungerade Anzahl von Bytes in Unicode zu lesen oder zu schreiben, führt zu einem Parametervalidierungsfehler. Wenn Sie Daten lesen oder schreiben möchten, die in Ihrem Programm als UTF-8 gespeichert sind, verwenden Sie den Text- oder Binärdateienmodus anstelle eines Unicode-Modus. Sie sind für jede erforderliche Kodierungsübersetzung verantwortlich.

Wenn **_sopen_s** aufgerufen wird und **_O_WRONLY** | **_O_APPEND** (Anfügemodus) und **_O_WTEXT**, **_O_ U16TEXT**, oder **_O_U8TEXT**, versucht sie zuerst Öffnen der Datei zum Lesen und schreiben, die BOM zu lesen, und öffnen Sie es erneut nur zum Schreiben. Wenn das Öffnen der Datei zum Lesen und Schreiben fehlschlägt, wird die Datei nur zum Schreiben geöffnet und der Standardwert für die Unicode-Moduseinstellung verwendet.

Das Argument *Shflag* ist ein konstanter Ausdruck, der eines der folgenden Manifestkonstanten besteht, die in definiert werden \<share.h >.

|*Shflag* Konstanten|Verhalten|
|-|-|
**_SH_DENYRW**|Verweigert den Lese- und Schreibzugriff auf eine Datei.
**_SH_DENYWR**|Verweigert den Schreibzugriff auf eine Datei.
**_SH_DENYRD**|Verweigert den Lesezugriff auf eine Datei.
**_SH_DENYNO**|Gestattet Lese- und Schreibzugriff.

Die *Pmode* Argument ist immer erforderlich, im Gegensatz zu in **_sopen**. Geben Sie bei **_O_CREAT**, wenn die Datei nicht vorhanden ist, *Pmode* gibt an, die berechtigungseinstellungen der Datei, die festgelegt werden, wenn die neue Datei zum ersten Mal geschlossen wird. Andernfalls *Pmode* wird ignoriert. *Pmode* ist ein Ganzzahlausdruck, der eine oder beide der Manifestkonstanten enthält **_S_IWRITE** und **_S_IREAD**, die definiert werden, \<sys\stat >. Wenn beide Konstanten verwendet werden, werden sie mithilfe des bitweisen OR-Operators kombiniert. Die Bedeutung der *Pmode* lautet wie folgt.

|*pmode*|Bedeutung|
|-|-|
**_S_IREAD**|Nur Lesen zugelassen.
**_S_IWRITE**|Schreiben zugelassen. (Lässt tatsächlich Lesen und Schreiben zu.)
**_S_IREAD** &AMP;#124; **_S_IWRITE**|Lesen und Schreiben erlaubt.

Wenn keine Schreibberechtigung gewährt wird, kann die Datei nur gelesen werden. Im Windows-Betriebssystem sind alle Dateien lesbar. Es ist nicht möglich, nur Schreibberechtigungen zu vergeben. Aus diesem Grund die Modi **_S_IWRITE** und **_S_IREAD** | **_S_IWRITE** sind gleichwertig.

**_sopen_s** gilt die aktuelle dateiberechtigungsmaske auf *Pmode* , bevor die Berechtigungen festgelegt sind. (Siehe [_umask](umask.md).)

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_sopen_s**|\<io.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>, \<share.h>|
|**_wsopen_s**|\<io.h> oder \<wchar.h>|\<fcntl.h>, \<sys/types.h>, \<sys/stat.h>, \<share.h>|

**_sopen_s** und **_wsopen_s** sind Microsoft-Erweiterungen. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_locking](locking.md).

## <a name="see-also"></a>Siehe auch

[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fsopen, _wfsopen](fsopen-wfsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
