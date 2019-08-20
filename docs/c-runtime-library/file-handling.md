---
title: Dateibehandlung
ms.date: 11/04/2016
f1_keywords:
- c.files
helpviewer_keywords:
- files [C++], handling
- files [C++], opening
- files [C++], manipulating
ms.assetid: 48119e2e-e94f-4602-b08b-b72440f731d8
ms.openlocfilehash: e5e43fe2cfcdfe067833d02bda511e8c9cb944ad
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500109"
---
# <a name="file-handling"></a>Dateibehandlung

Verwenden Sie diese Routinen zum Erstellen, Löschen und Bearbeiten von Dateien und zum Überprüfen der Dateizugriffsberechtigungen.

Bei C-Laufzeitbibliotheken können maximal 512 Dateien gleichzeitig geöffnet sein. Wenn Sie versuchen, mehr als die maximale Anzahl von Dateideskriptoren oder Dateistreams zu öffnen, kommt es zu einem Programmfehler. Mit [_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md) können Sie diese Anzahl ändern.

## <a name="file-handling-routines-file-descriptor"></a>Dateibehandlungsroutinen (Dateideskriptor)

Diese Routinen werden auf Dateien ausgeführt, die durch einen Dateideskriptor festgelegt sind.

|-Routine zurückgegebener Wert|Mit|
|-------------|---------|
|[_chsize](../c-runtime-library/reference/chsize.md),[_chsize_s](../c-runtime-library/reference/chsize-s.md)|Dateigröße ändern|
|[_filelength, _filelengthi64](../c-runtime-library/reference/filelength-filelengthi64.md)|Dateilänge abrufen|
|[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)|Dateistatusinformationen zum Deskriptor abrufen|
|[_get_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Betriebssystem-Dateihandle zurückgeben, das vorhandenem C-Laufzeit-Dateideskriptor zugeordnet ist|
|[_isatty](../c-runtime-library/reference/isatty.md)|Auf Zeichengerät überprüfen|
|[_locking](../c-runtime-library/reference/locking.md)|Dateibereiche sperren|
|[_open_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|C-Laufzeit-Dateideskriptor zu vorhandenem Betriebssystem-Dateihandle zuordnen|
|[_setmode](../c-runtime-library/reference/setmode.md)|Dateiübersetzungsmodus festlegen|

## <a name="file-handling-routines-path-or-filename"></a>Dateibehandlungsroutinen (Pfad oder Dateiname)

Diese Routinen werden auf Dateien ausgeführt, die durch einen Pfad oder einen Dateinamen angegeben sind.

|-Routine zurückgegebener Wert|Verwendung|
|-------------|---------|
|[_access, _waccess](../c-runtime-library/reference/access-waccess.md), [_access_s, _waccess_s](../c-runtime-library/reference/access-s-waccess-s.md)|Dateiberechtigungseinstellung überprüfen|
|[_chmod, _wchmod](../c-runtime-library/reference/chmod-wchmod.md)|Dateiberechtigungseinstellung ändern|
|[_fullpath, _wfullpath](../c-runtime-library/reference/fullpath-wfullpath.md)|Relativen Pfad auf den absoluten Pfadnamen erweitern|
|[_makepath, _wmakepath](../c-runtime-library/reference/makepath-wmakepath.md), [_makepath_s, _wmakepath_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|Pfadkomponenten in einen einzelnen, vollständigen Pfad zusammenführen|
|[_mktemp, _wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md), [_mktemp_s, _wmktemp_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|Eindeutigen Dateinamen erstellen|
|[remove, _wremove](../c-runtime-library/reference/remove-wremove.md)|Datei löschen|
|[rename, _wrename](../c-runtime-library/reference/rename-wrename.md)|Datei umbenennen|
|[_splitpath, _wsplitpath](../c-runtime-library/reference/splitpath-wsplitpath.md), [_splitpath_s, _wsplitpath_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|Pfad nach Komponenten analysieren|
|[_stat, _stat64, _stati64, _wstat, _wstat64, _wstati64](../c-runtime-library/reference/stat-functions.md)|Dateistatusinformationen zur benannten Datei abrufen|
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Standardberechtigungsmaske für neue Dateien festlegen, die vom Programm erstellt werden|
|[_unlink, _wunlink](../c-runtime-library/reference/unlink-wunlink.md)|Datei löschen|

## <a name="file-handling-routines-open-file"></a>Dateibehandlungsroutinen (geöffnete Datei)

Diese Routinen öffnen Dateien.

|-Routine zurückgegebener Wert|Verwendung|
|-------------|---------|
|[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Öffnet eine Datei und gibt einen Zeiger an die geöffnete Datei zurück.|
|[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Öffnet einen Stream mit Dateifreigabe und gibt einen Zeiger an die geöffnete Datei zurück.|
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|Öffnet eine Datei und gibt einen Dateideskriptor an die geöffnete Datei zurück.|
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Öffnet eine Datei mit Dateizugriff und gibt einen Dateideskriptor an die geöffnete Datei zurück.|
|[_pipe](../c-runtime-library/reference/pipe.md)|Erstellt eine Pipe zum Lesen und Schreiben.|
|[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s, _wfreopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Weist einen Dateizeiger neu zu.|

Diese Routinen bieten eine Möglichkeit, die Darstellung der Datei zwischen einer `FILE`-Struktur, einem Dateideskriptor und einem Win32-Dateihandle zu ändern.

|-Routine zurückgegebener Wert|Verwendung|
|-------------|---------|
|[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|Ordnet einen Stream einer Datei zu, die zuvor für E/A-Unterstützung auf niedriger Ebene geöffnet wurde, und gibt einen Zeiger an den geöffneten Stream zurück.|
|[_fileno](../c-runtime-library/reference/fileno.md)|Ruft den Dateideskriptor ab, der einem Stream zugeordnet ist.|
|[_get_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Betriebssystem-Dateihandle zurückgeben, das vorhandenem C-Laufzeit-Dateideskriptor zugeordnet ist|
|[_open_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|Ordnet den C-Laufzeit-Dateideskriptor einem vorhandenen Betriebssystem-Dateihandle zu.|

Mit den folgenden Win32-Funktionen werden auch Dateien und Pipes geöffnet:

- [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilew)

- [CreatePipe](/windows/win32/api/namedpipeapi/nf-namedpipeapi-createpipe)

- [CreateNamedPipe](/windows/win32/api/winbase/nf-winbase-createnamedpipew)

## <a name="see-also"></a>Siehe auch

[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Verzeichnissteuerung](../c-runtime-library/directory-control.md)<br/>
[Systemaufrufe](../c-runtime-library/system-calls.md)<br/>
