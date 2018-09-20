---
title: Im Menü Datei, in einer MFC-Datenbankanwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- File menu
- database applications [MFC], File menu commands
ms.assetid: 92dafb75-c1b3-4860-80a0-87a83bfc36f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5fe90e01ec53711f47418d4512262e2e05e62f26
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425131"
---
# <a name="file-menu-in-an-mfc-database-application"></a>Das Dateimenü in einer MFC-Datenbankanwendung

Wenn Sie eine MFC-datenbankanwendung erstellen und Sie keine Serialisierung verwenden, wie sollten Sie interpretiert das Öffnen, schließen, speichern, und speichern als Befehle, auf das Menü "Datei" Es gibt, zwar keine Stilrichtlinien für diese Frage hier sind einige Vorschläge:

- Beseitigen Sie Befehl zum Öffnen des Menüs Datei vollständig.

- Interpretieren Sie den Befehl "Öffnen" als "open Database" aus, und zeigt Sie dem Benutzer eine Liste der Datenquellen, die der Anwendung erkannt.

- Interpretieren Sie den Befehl "Öffnen", z. B., "Profil geöffnet werden." Sollen Sie öffnen Sie für das Öffnen einer serialisierten Datei, aber zum Speichern einer serialisierten Dokuments mit "Benutzerprofil" Informationen wie die Einstellungen des Benutzers, einschließlich seiner verwenden Sie die Datei oder ihre Anmelde-ID (optional außer das Kennwort) und die Datenquellen er am häufigsten beibehalten werden vor kurzem hat.

Den MFS-Anwendungsassistenten unterstützt das Erstellen einer Anwendung mit keine dokumentbezogene dateimenübefehle. Wählen Sie die **-Datenbanksicht ohne dateiunterstützung** option die **-Datenbanken unterstützen** Seite.

Um einen Menübefehl für die Datei auf besondere Weise interpretieren zu können, müssen Sie eine oder mehrere Befehlshandler, überschreiben, meist in Ihre `CWinApp`-abgeleitete Klasse. Angenommen, Sie vollständig außer Kraft setzen `OnFileOpen` (implementiert die `ID_FILE_OPEN` Befehl) bedeutet "Datenbank öffnen:"

- Rufen Sie nicht die Basisklassenversion von `OnFileOpen`, da Sie das Framework die standardmäßige Implementierung des Befehls vollständig ersetzen.

- Verwenden Sie stattdessen den Handler, um ein Dialogfeld, das Auflisten von Datenquellen anzuzeigen. Sie können ein derartiges Dialogfeld anzeigen, durch den Aufruf `CDatabase::OpenEx` oder `CDatabase::Open` mit dem Parameter **NULL**. Daraufhin wird ein ODBC-Dialogfeld, in dem alle verfügbaren Datenquellen auf dem Computer des Benutzers angezeigt.

- Da nicht-datenbankanwendungen in der Regel auf ein vollständiges Dokument speichern, Sie werden wahrscheinlich Speichern entfernen möchten, und speichern Sie als Implementierungen, wenn Sie ein Dokument serialisiertes verwenden, um Profilinformationen zu speichern. Andernfalls können Sie den Befehl "Speichern", z. B. "Transaktion ein commit." implementieren Finden Sie unter [technischen Hinweis 22](../mfc/tn022-standard-commands-implementation.md) für Weitere Informationen zum Überschreiben dieser Befehle.

## <a name="see-also"></a>Siehe auch

[Serialisierung: Serialisierung im Vergleich zur Datenbankeingabe/-Ausgabe](../mfc/serialization-serialization-vs-database-input-output.md)

