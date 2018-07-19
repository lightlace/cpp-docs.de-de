---
title: Verzeichnissteuerung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], directory
- directory control routines
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c0ab24a55cddc13b743a28a022475b0c0b84e77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389727"
---
# <a name="directory-control"></a>Verzeichnissteuerung

Diese Routinen greifen auf die Verzeichnisstruktur zu, ändern sie und rufen Informationen dazu ab.

## <a name="directory-control-routines"></a>Routinen für die Verzeichnissteuerung

|-Routine zurückgegebener Wert|Mit|
|-------------|---------|
|[_chdir, _wchdir](../c-runtime-library/reference/chdir-wchdir.md)|Ändert das aktuelle Arbeitsverzeichnis.|
|[_chdrive](../c-runtime-library/reference/chdrive.md)|Ändert das aktuelle Laufwerk.|
|[_getcwd, _wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Ruft das aktuelle Arbeitsverzeichnis für das Standardlaufwerk ab.|
|[_getdcwd, _wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Ruft das aktuelle Arbeitsverzeichnis für das angegebene Laufwerk ab.|
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|Füllt eine **_diskfree_t**-Struktur mit Informationen über ein Laufwerk auf.|
|[_getdrive](../c-runtime-library/reference/getdrive.md)|Ruft das aktuelle (standardmäßige) Laufwerk ab.|
|[_getdrives](../c-runtime-library/reference/getdrives.md)|Gibt eine Bitmaske zurück, die die aktuell verfügbaren Laufwerke darstellt.|
|[_mkdir, _wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|Erstellt ein neues Verzeichnis.|
|[_rmdir, _wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Verzeichnis entfernen|
|[_searchenv, _wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [_searchenv_s, _wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Sucht nach der angegebenen Datei in den angegebenen Pfaden.|

## <a name="see-also"></a>Siehe auch

[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
 [Dateibehandlung](../c-runtime-library/file-handling.md)<br/>
 [Systemaufrufe](../c-runtime-library/system-calls.md)<br/>
