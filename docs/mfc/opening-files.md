---
title: Öffnen von Dateien
ms.date: 11/04/2016
helpviewer_keywords:
- Open member functions [MFC]
- CFile class [MFC], variable
- opening files, in MFC
- Open calls [MFC]
- Open method, CFile class [MFC]
- examples [MFC], opening files
- opening files, handling exceptions
- exception handling [MFC], when opening files
- files [MFC], opening
- file objects [MFC]
- MFC, file operations
- opening files [MFC]
- exception handling [MFC], opening files
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
ms.openlocfilehash: dab7a680d9b33a6e334da99a045b709fe00f215c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394480"
---
# <a name="opening-files"></a>Öffnen von Dateien

In MFC ist die gängigste Methode zum Öffnen einer Datei ein zweistufiger Prozess.

#### <a name="to-open-a-file"></a>Zum Öffnen einer Datei

1. Erstellen Sie das Objekt "Datei", ohne einen Pfad oder die Berechtigung-Flags.

   Sie erstellen ein Objekt "Datei" in der Regel durch Deklarieren einer [CFile](../mfc/reference/cfile-class.md) Variablen im Stapelrahmen.

1. Rufen Sie die [öffnen](../mfc/reference/cfile-class.md#open) Member-Funktion für das File-Objekt, einen Pfad und der Berechtigung Flags angeben.

   Der Rückgabewert für `Open` werden ungleich NULL, wenn die Datei erfolgreich geöffnet wurde, oder 0, wenn die angegebene Datei konnte nicht geöffnet werden. Die `Open` Member-Funktion wird wie folgt:

   `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`

   Die open-Flags festlegen, welche Berechtigungen ein, z. B. schreibgeschützt, Sie möchten, für die Datei. Die möglichen Flagwerte sind definiert als aufgezählte Konstanten in der `CFile` Klasse, damit sie mit gekennzeichnet sind "`CFile::`" wie in `CFile::modeRead`. Verwenden der `CFile::modeCreate` auszugeben, wenn Sie die Datei erstellen möchten.

Das folgende Beispiel zeigt, wie Sie eine neue Datei mit Lese-/Schreibberechtigung (ersetzen Sie alle vorherige Datei mit dem gleichen Pfad) zu erstellen:

[!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]

> [!NOTE]
>  In diesem Beispiel erstellt und öffnet eine Datei. Wenn Probleme auftreten, die `Open` Aufruf zurückgeben kann eine `CFileException` Objekt in der letzte Parameter, wie hier gezeigt. Das TRACE-Makro gibt sowohl den Dateinamen und einen Code, der angibt, der Ursache für Fehler. Rufen Sie die `AfxThrowFileException` ausgeführt werden, wenn gewünscht, ausführlichere-Fehlerberichterstattung.

## <a name="see-also"></a>Siehe auch

[CFile-Klasse](../mfc/reference/cfile-class.md)<br/>
[CFile::Open](../mfc/reference/cfile-class.md#open)<br/>
[Dateien](../mfc/files-in-mfc.md)
