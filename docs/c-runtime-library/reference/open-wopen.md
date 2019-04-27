---
title: _open, _wopen
ms.date: 11/04/2016
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
ms.openlocfilehash: 7ef28d6cafa0b74b50ee2c50ec380b8bd3aed79f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156083"
---
# <a name="open-wopen"></a>_open, _wopen

Öffnet eine Datei. Diese Funktionen sind veraltet, da sichere Versionen verfügbar sind; siehe [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md).

## <a name="syntax"></a>Syntax

```C
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

### <a name="parameters"></a>Parameter

*filename*<br/>
Dateiname

*oflag*<br/>
Die zulässige Art von Vorgängen.

*pmode*<br/>
Berechtigungsmodus.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Dateideskriptor für die geöffnete Datei zurück. Der Rückgabewert 1 gibt an, ein Fehler; In diesem Fall **Errno** auf einen der folgenden Werte festgelegt ist.

|errno-Wert|Bedingung|
|-|-|
| **EACCES** | Versuch, eine schreibgeschützte Datei zum Schreiben zu öffnen, der Freigabemodus der Datei lässt die angegebenen Vorgänge nicht zu, oder der vorgegebene Pfad ist ein Verzeichnis. |
| **EEXIST** | **_O_CREAT** und **_O_EXCL** Flag angegeben, aber *Filename* ist bereits vorhanden. |
| **EINVAL** | Ungültige *Oflag* oder *Pmode* Argument. |
| **EMFILE** | Es sind keine weiteren Dateideskriptoren verfügbar (zu viele Dateien sind geöffnet). |
| **ENOENT** | Datei oder Pfad nicht gefunden. |

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_open** -Funktion öffnet die angegebene Datei *Filename* und bereitet es für das Lesen oder schreiben, die laut vor *Oflag*. **_WOpen** ist eine Breitzeichen-Version von **_open**; die *Filename* Argument **_wopen** ist eine Breitzeichen-Zeichenfolge. **_WOpen** und **_open** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_topen**|**_open**|**_open**|**_wopen**|

*Oflag* ist ein Ganzzahlausdruck aus einer oder mehreren der folgenden Manifestkonstanten oder konstantenkombinationen gebildet wurde, die definiert sind \<fcntl.h >.

|*Oflag* Konstanten|Verhalten|
|-|-|
| **_O_APPEND** | Verschiebt den Dateizeiger vor jedem Schreibvorgang an das Ende der Datei. |
| **_O_BINARY** | Öffnet die Datei im Binärmodus (nicht übersetzt). (Eine Beschreibung des binären Modus finden Sie unter [fopen](fopen-wfopen.md).) |
| **_O_CREAT** | Erstellt eine Datei und öffnet sie zum Schreiben. Hat keine Auswirkungen, wenn die Datei durch angegeben *Filename* vorhanden ist. Die *Pmode* Argument ist erforderlich, wenn **_O_CREAT** angegeben ist. |
| **_O_CREAT** &#124; **_O_SHORT_LIVED** | Erstellt eine temporäre Datei und leert sie, wenn möglich, nicht auf die Festplatte. Die *Pmode* Argument ist erforderlich, wenn **_O_CREAT** angegeben ist. |
| **_O_CREAT** &#124; **_O_TEMPORARY** | Erstellt eine temporäre Datei. Die Datei wird gelöscht, wenn der letzte Dateideskriptor geschlossen wird. Die *Pmode* Argument ist erforderlich, wenn **_O_CREAT** angegeben ist. |
| **_O_CREAT** &#124; ` _O_EXCL` | Gibt einen Fehlerwert zurück, wenn eine Datei, die anhand des *Filename* vorhanden ist. Gilt nur bei Verwendung mit **_O_CREAT**. |
| **_O_NOINHERIT** | Verhindert die Erstellung eines gemeinsam verwendeten Dateideskriptors. |
| **_O_RANDOM** | Gibt an, dass das Zwischenspeichern für den zufälligen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist. |
| **_O_RDONLY** | Öffnet eine Datei nur zum Lesen. Kann nicht angegeben werden, mit **_O_RDWR** oder **_O_WRONLY**. |
| **_O_RDWR** | Öffnet eine Datei zum Lesen und zum Schreiben. Kann nicht angegeben werden, mit **_O_RDONLY** oder **_O_WRONLY**. |
| **_O_SEQUENTIAL** | Gibt an, dass das Zwischenspeichern für den sequenziellen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist. |
| **_O_TEXT** | Öffnet eine Datei im Textmodus (übersetzt). (Weitere Informationen finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [fopen](fopen-wfopen.md).) |
| **_O_TRUNC** | Öffnet eine Datei und verkürzt sie auf die Länge Null. Für die Datei muss Schreibberechtigung bestehen. Kann nicht angegeben werden, mit **_O_RDONLY**. **_O_TRUNC** mit verwendet **_O_CREAT** öffnet eine vorhandene Datei oder erstellt eine Datei. **Hinweis**: Die **_O_TRUNC** Flag zerstört die Inhalte der angegebenen Datei. |
| **_O_WRONLY** | Öffnet eine Datei nur zum Schreiben. Kann nicht angegeben werden, mit **_O_RDONLY** oder **_O_RDWR**. |
| **_O_U16TEXT** | Öffnet eine Datei im Unicode-UTF-16-Modus. |
| **_O_U8TEXT** | Öffnet eine Datei im Unicode-UTF-8-Modus. |
| **_O_WTEXT** | Öffnet eine Datei im Unicode-Modus. |

Um den Zugriffsmodus für die Datei anzugeben, geben Sie **_O_RDONLY**, **_O_RDWR**, oder **_O_WRONLY**. Es gibt keinen Standardwert für den Zugriffsmodus.

Wenn **_O_WTEXT** wird verwendet, um eine Datei zum Lesen öffnen **_open** liest den Anfang der Datei, und überprüft, ob eine Byte-reihenfolgemarkierung (BOM). Wenn eine BOM vorhanden ist, wird die Datei je nach BOM als UTF-8 oder UTF-16LE behandelt. Wenn keine BOM vorhanden ist, wird die Datei als ANSI behandelt. Wenn eine Datei geöffnet zum Schreiben mit **_O_WTEXT**, UTF-16 verwendet. Unabhängig von früheren Einstellungen oder bytereihenfolgemarkierungen order Mark, wenn **_O_U8TEXT** wird verwendet, die Datei wird immer geöffnet als UTF-8; Wenn **_O_U16TEXT** wird verwendet, wird diese Datei immer als UTF-16 geöffnet.

Wenn eine Datei im Unicode-Modus mit geöffnet wird **_O_WTEXT**, **_O_U8TEXT**, oder **_O_U16TEXT**Eingabe übersetzen Eingabefunktionen die Daten, die aus der Datei in UTF-16-Daten gelesen werden gespeichert als Typ **"wchar_t"**. Funktionen, die für eine im Unicode-Modus geöffnete Datei zu schreiben, erwarten Puffer, die UTF-16-Daten als Typ enthalten **"wchar_t"**. Wenn eine Datei als UTF-8 kodiert ist, dann werden UTF-16-Daten beim Schreiben in UTF-8 übersetzt, und die UTF-8-kodierten Inhalte der Datei werden beim Lesen in UTF-16 übersetzt. Der Versuch, in diesem Modus eine ungerade Anzahl von Bytes in Unicode zu lesen oder zu schreiben, führt zu einem Parametervalidierungsfehler. Wenn Sie Daten lesen oder schreiben möchten, die in Ihrem Programm als UTF-8 gespeichert sind, verwenden Sie den Text- oder Binärdateienmodus anstelle eines Unicode-Modus. Sie sind für jede erforderliche Kodierungsübersetzung verantwortlich.

Wenn **_open** aufgerufen wird und **_O_WRONLY** | **_O_APPEND** (Anfügemodus) und **_O_WTEXT**, **_O_ U16TEXT**, oder **_O_U8TEXT**, zuerst wird versucht, das Öffnen der Datei zum Lesen und schreiben, die BOM zu lesen, und öffnen Sie es erneut nur zum Schreiben. Wenn das Öffnen der Datei zum Lesen und Schreiben fehlschlägt, wird die Datei nur zum Schreiben geöffnet und der Standardwert für die Unicode-Moduseinstellung verwendet.

Wenn zwei oder mehr Manifestkonstanten verwendet werden, zu der *Oflag* -Argument, werden die Konstanten mit dem bitweisen OR-Operator kombiniert ( **&#124;** ). Eine Darstellung des Binär- und Textmodus finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

Die *Pmode* Argument ist erforderlich, nur, wenn **_O_CREAT** angegeben ist. Wenn die Datei bereits vorhanden ist, *Pmode* wird ignoriert. Andernfalls *Pmode* gibt die dateiberechtigungseinstellungen an, die festgelegt werden, wenn die neue Datei zum ersten Mal geschlossen wird. **_open** wendet auf die aktuelle dateiberechtigungsmaske *Pmode* , bevor die Berechtigungen festgelegt sind. (Weitere Informationen finden Sie unter [_umask](umask.md).) *Pmode* ist ein Ganzzahlausdruck, der enthält eine oder beide der folgenden Manifestkonstanten, die definiert sind \<sys\stat >.

|*pmode*|Bedeutung|
|-|-|
| **_S_IREAD** | Nur Lesen zugelassen. |
| **_S_IWRITE** | Schreiben zugelassen. (Lässt tatsächlich Lesen und Schreiben zu.) |
| **_S_IREAD** &#124; **_S_IWRITE** | Lesen und Schreiben erlaubt. |

Wenn beide Konstanten gegeben sind, werden sie mit dem bitweisen OR-Operator verbunden ( **&#124;** ). In Windows sind alle Dateien lesbar, eine schreibgeschützte Berechtigung ist nicht verfügbar. Daher sind die Modi **_S_IWRITE** und **_S_IREAD** | **_S_IWRITE** entsprechen.

Wenn ein anderer Wert als eine Kombination **_S_IREAD** und **_S_IWRITE** für angegeben wird *Pmode*– selbst wenn sie einen gültigen angeben würde *Pmode*in einem anderen Betriebssystem, oder wenn ein anderer als die zulässigen Wert *Oflag* Werte angegeben wird, die Funktion eine Assertion im Debugmodus generiert und der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktion gibt-1 zurück und legt **Errno** zu **EINVAL**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_open**|\<io.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>|
|**_wopen**|\<io.h> oder \<wchar.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>|

**_open** und **_wopen** sind Microsoft-Erweiterungen. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
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

### <a name="output"></a>Output

```Output
Open succeeded on input file
Open succeeded on output file
```

## <a name="see-also"></a>Siehe auch

[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
