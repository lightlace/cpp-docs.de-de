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
ms.openlocfilehash: fb1a523ca82cd8e1a4256da657efe9702517beda
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907350"
---
# <a name="wizards-and-the-resource-editors"></a>Assistenten und der Ressourcen-Editor

Visual C++ bietet verschiedene Assistenten für die Verwendung in der MFC-Programmierung sowie viele integrierte Ressourcen-Editoren. Beim Programmieren von ActiveX- [Steuer](../mfc/reference/mfc-activex-control-wizard.md) Elementen bedient sich der ActiveX-Steuerelement-Assistent ähnlich wie der MFC-Anwendungs-Assistent. Obwohl Sie MFC-Anwendungen ohne die meisten dieser Tools schreiben können, vereinfachen und beschleunigen die Tools Ihre Arbeit erheblich.

##  <a name="_core_use_appwizard_to_create_an_mfc_application"></a>Verwenden des MFC-Anwendungs-Assistenten zum Erstellen einer MFC-Anwendung

Verwenden Sie den [MFC-Anwendungs-Assistenten](../mfc/reference/mfc-application-wizard.md) , um ein MFC C++-Projekt in Visual zu erstellen, das OLE-und Datenbankunterstützung einschließen kann. Dateien im Projekt enthalten die Klassen "Anwendung", "Dokument", "Ansicht" und "Rahmen Fenster". Standard Ressourcen, einschließlich Menüs und einer optionalen Symbolleiste Weitere erforderliche Windows-Dateien; und optionale RTF-Dateien mit Windows-Standard Hilfe Themen, die Sie überarbeiten und erweitern können, um die Hilfedatei des Programms zu erstellen.

##  <a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a>Verwenden von Klassenansicht zum Verwalten von Klassen und Windows-Meldungen

Klassenansicht unterstützt Sie beim Erstellen von Handlerfunktionen für Windows-Meldungen und-Befehle, erstellen und Verwalten von Klassen, Erstellen von Klassenmember-Variablen, Erstellen von Automatisierungsmethoden und-Eigenschaften, Erstellen von Datenbankklassen und

> [!NOTE]
>  Klassenansicht hilft Ihnen auch, virtuelle Funktionen in den MFC-Klassen zu überschreiben. Wählen Sie die Klasse und die zu über schreibende virtuelle Funktion aus. Der restliche Prozess ähnelt der Nachrichten Behandlung, wie in den folgenden Abschnitten beschrieben.

Anwendungen, die unter Windows ausgeführt werden, sind [Nachrichten gesteuert](../mfc/message-handling-and-mapping.md). Benutzeraktionen und andere Ereignisse, die im laufenden Programm auftreten, bewirken, dass Windows Meldungen im Programm an die Fenster sendet. Wenn der Benutzer z. b. in einem Fenster auf die Maus klickt, sendet Windows eine WM_LBUTTONDOWN-Meldung, wenn die linke Maustaste gedrückt wird, und eine WM_LBUTTONUP-Meldung, wenn die Schaltfläche losgelassen wird. Windows sendet auch WM_COMMAND-Nachrichten, wenn der Benutzer Befehle in der Menüleiste auswählt.

Im MFC-Framework können verschiedene Objekte (z. b. Dokumente, Sichten, Rahmen Fenster, Dokumentvorlagen und das Anwendungs Objekt) Nachrichten verarbeiten. Ein solches Objekt stellt eine "Handlerfunktion" als eine seiner Member-Funktionen bereit, und das Framework ordnet die eingehende Nachricht dem Handler zu.

Ein großer Teil der Programmieraufgabe ist das Auswählen der Nachrichten, die den Objekten zugeordnet werden sollen, und die anschließende Implementierung dieser Zuordnung. Verwenden Sie hierzu Klassenansicht und den-Klassen- [Assistenten](reference/mfc-class-wizard.md).

Der [Klassen-Assistent](reference/mfc-class-wizard.md) erstellt leere nachrichtenhandlermember-Funktionen, und Sie verwenden den Quell Code-Editor, um den Text des Handlers zu implementieren. Sie können auch Klassen (einschließlich der eigenen Klassen, die nicht von MFC-Klassen abgeleitet sind) und ihre Member mit Klassenansicht erstellen oder bearbeiten. Weitere Informationen zur Verwendung von Klassenansicht und zu Assistenten, die einem Projekt Code hinzufügen, finden Sie unter [Hinzufügen von Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md).

##  <a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a>Verwenden der Ressourcen-Editoren zum Erstellen und Bearbeiten von Ressourcen

Verwenden Sie die C++ visuellen [Ressourcen-Editoren](../windows/resource-editors.md) zum Erstellen und Bearbeiten von Menüs, Dialogfeldern, benutzerdefinierten Steuerelementen, Zugriffstasten, Bitmaps, Symbolen, Cursorn, Zeichen folgen und Versions Ressourcen. Ab der visuellen C++ Version 4,0 vereinfacht ein Symbolleisten-Editor das Erstellen von Symbolleisten erheblich.

Der Microsoft Foundation Class-Bibliothek stellt eine Datei namens "Common" bereit, um Ihnen noch mehr zu helfen. RES, das "Clip Art"-Ressourcen enthält, die Sie von Common kopieren können. Fügen Sie Ihre eigene Ressourcen Datei ein, und fügen Sie Sie ein. Gewöhnliche. RES umfasst Symbolleisten Schaltflächen, gängige Cursor, Symbole und vieles mehr. Sie können diese Ressourcen in Ihrer Anwendung verwenden, ändern und neu verteilen. Weitere Informationen zu Common. Zu res finden Sie im [Beispiel zu ClipArt](../overview/visual-cpp-samples.md).

Der MFC-Anwendungs-Assistent, C++ die visuellen Assistenten, Ressourcen-Editoren und das MFC-Framework erledigen viel Arbeit für Sie und vereinfachen die Verwaltung Ihres Codes erheblich. Der Großteil des anwendungsspezifischen Codes befindet sich in ihren Dokument-und Ansichts Klassen.

## <a name="see-also"></a>Siehe auch

[Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
