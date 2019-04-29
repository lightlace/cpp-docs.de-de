---
title: Zugreifen auf den Dateistatus
ms.date: 11/04/2016
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
ms.openlocfilehash: 26c263b2d7e4e0243444925cb9416cb337dcd79d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392959"
---
# <a name="accessing-file-status"></a>Zugreifen auf den Dateistatus

`CFile` unterstützt Sie auch das Abrufen der Status der Datei, z. B., ob die Datei vorhanden ist, Erstellung und Änderung von Datumsangaben und Uhrzeiten, logische Größe und Pfad.

### <a name="to-get-file-status"></a>Zum Abrufen des Dateistatus

1. Verwenden der [CFile](../mfc/reference/cfile-class.md) Klasse zum Abrufen und Festlegen von Informationen zu einer Datei. Eine nützliche Anwendung ist die Verwendung der `CFile` statische Memberfunktion **GetStatus** zu bestimmen, ob eine Datei vorhanden ist. **GetStatus** gibt 0 zurück, wenn die angegebene Datei nicht vorhanden ist.

Daher können Sie das Ergebnis des **GetStatus** zu bestimmen, ob mit der **modeCreate** flag an, wenn das Öffnen einer Datei, wie im folgenden Beispiel gezeigt:

[!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]

Weitere Informationen finden Sie unter [Serialisierung](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Siehe auch

[Dateien](../mfc/files-in-mfc.md)
