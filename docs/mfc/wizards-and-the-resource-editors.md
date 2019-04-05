---
title: Assistenten und der Ressourcen-Editor
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and MFC
- MFC, resource editors
- resource editors, MFC
- MFC Application Wizard
- editors [MFC], resource
- wizards [MFC]
- wizards [MFC], MFC programming
- MFC, wizards
- Class View tool, managing Windows messages
ms.assetid: f5dd4d13-9dc1-4a49-b6bf-5b3cb45fa8ba
ms.openlocfilehash: 41cbb86b4245bd78baecd222b5573ba5e877243a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773826"
---
# <a name="wizards-and-the-resource-editors"></a>Assistenten und der Ressourcen-Editor

Visual C++ enthält mehrere Assistenten für die Verwendung in MFC-Programmierung, zusammen mit vielen integrierten Ressourcen-Editoren. Für ActiveX-Programmieren Steuerelemente, die [ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md) dient einem Zweck ähnlich der MFC-Anwendung-Assistenten. Während Sie die MFC-Anwendungen, ohne die meisten dieser Tools schreiben können, werden von den Tools erheblich vereinfachen und beschleunigen Ihre Arbeit.

##  <a name="_core_use_appwizard_to_create_an_mfc_application"></a> Verwenden Sie den Assistenten zum MFC-Anwendungen zum Erstellen einer Mfc_anwendung

Verwenden der [MFS-Anwendungsassistenten](../mfc/reference/mfc-application-wizard.md) ein MFC-Projekt in Visual C++ zu erstellen, die OLE enthalten und datenbankunterstützung können. Dateien im Projekt enthalten, Ihre Anwendung, Dokument, Ansicht und Rahmenfensterklassen; Standard-Ressourcen, einschließlich Menüs und eine optionale Symbolleiste; andere erforderliche Dateien für Windows; und optionale RTF-Dateien enthält, die standardmäßige Windows-Hilfethemen, die Sie ändern können, und ergänzen Hilfedatei des Programms zu erstellen.

##  <a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a> Mithilfe der Klassenansicht zum Verwalten von Klassen und Windows-Meldungen

Klasse Ansicht können Sie Handlerfunktionen für Windows-Meldungen und Befehle erstellen, erstellen und Verwalten von Klassen, Klassenmember Variablen erstellen, Erstellen von Automation-Methoden und Eigenschaften, die Datenbankklassen und vieles mehr zu erstellen.

> [!NOTE]
>  Klassenansicht hilft Ihnen auch die virtuelle Funktionen in die MFC-Klassen außer Kraft setzen möchten. Wählen Sie die Klasse und die zu überschreibende virtuelle Funktion. Die restlichen Prozess ähnelt der Behandlung von Nachrichten, wie in den folgenden Abschnitten beschrieben.

Anwendungen, die unter Windows ausgeführt wird, sind [Message driven](../mfc/message-handling-and-mapping.md). Führen Windows zum Senden von Nachrichten an die Fenster in das Programm, Benutzeraktionen und andere Ereignisse, die in das aktive Programm auftreten. Z. B. wenn der Benutzer den Mauszeiger über einem Fenster klickt, sendet Windows eine WM_LBUTTONDOWN-Meldung, wenn die linke Maustaste gedrückt wird und eine Nachricht ein WM_LBUTTONUP, wenn die Maustaste losgelassen wird. Windows sendet auch WM_COMMAND-Meldungen auf, wenn der Benutzer Befehle in der Menüleiste auswählt.

In MFC-Framework können verschiedene Objekte, z. B. Dokumente, Ansichten, Rahmenfenster, Dokumentvorlagen und des Anwendungsobjekts, "Nachrichten behandeln". Ein solches Objekt eine "Handlerfunktion" als eines seiner Member stellt Funktionen bereit, und das Framework wird die eingehende Nachricht der Handler zugeordnet.

Ein großer Teil der Ihre Aufgabe als Programmierer ist die Auswahl der Nachrichten, auf welche Objekte zuzuordnen und implementieren Sie dann auf die Zuordnung. Zu diesem Zweck verwenden Sie Klassenansicht und im Eigenschaftenfenster angezeigt.

Das Fenster "Eigenschaften" erstellt ein leeres Meldungshandler-Memberfunktionen, und Sie den Quellcode-Editor verwenden, um den Text des ereignishandlers zu implementieren. Sie können auch erstellen oder Bearbeiten von Klassen (einschließlich Ihrer eigenen, nicht von MFC-Klassen abgeleitete Klassen) und deren Member in der Klassenansicht. Weitere Informationen zur Verwendung der Klassenansicht und Assistenten, mit denen einer Projekt Code hinzu, finden Sie unter [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md).

##  <a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a> Verwenden Sie die Ressourcen-Editoren zum Erstellen und Bearbeiten von Ressourcen

Verwenden Sie die Visual C++ [Ressourcen-Editoren](../windows/resource-editors.md) erstellen und Bearbeiten von Menüs, Dialogfeldern, benutzerdefinierte Steuerelemente, Zugriffstasten, Bitmaps, Symbole, Cursor, Zeichenfolgen und Versionsressourcen. Ab Visual C++, Version 4.0 vereinfacht ein Symbolleisten-Editor Erstellen von Symbolleisten.

Damit Sie noch mehr, bietet die Microsoft Foundation Class-Library eine Datei mit dem allgemeinen. RES, die "ClipArt-Ressourcen enthält, die Sie häufiger kopieren können. RES, und fügen Sie in Ihren eigenen Ressourcendatei. ALLGEMEINE. RES enthält Schaltflächen der Symbolleiste, allgemeine Cursor, Symbole und vieles mehr. Sie können verwenden, ändern und verteilen diese Ressourcen in Ihrer Anwendung. Weitere Informationen zu allgemeinen. RES, finden Sie unter den [Clipart-Beispiel](../overview/visual-cpp-samples.md).

Den Assistenten zum MFC-Anwendungen, die Visual C++-Assistenten, Ressourcen-Editoren und MFC-Framework viel Arbeit für Sie erledigt, und vereinfachen der Verwaltung von Ihrem Codes viel einfacher. Der größte Teil Ihrer Anwendung-spezifischen Code befindet sich in Ihrem Dokument und Anzeigen von Klassen.

## <a name="see-also"></a>Siehe auch

[Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
