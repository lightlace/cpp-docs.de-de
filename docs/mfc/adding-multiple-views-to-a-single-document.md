---
title: Hinzufügen mehrerer Ansichten zu einem Dokument
ms.date: 11/04/2016
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
ms.openlocfilehash: 593c59c73b58b4364c9d652ce8eb415c17af496c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767586"
---
# <a name="adding-multiple-views-to-a-single-document"></a>Hinzufügen mehrerer Ansichten zu einem Dokument

In einer Single Document Interface (SDI)-Anwendung mit der Microsoft Foundation Class (MFC)-Bibliothek erstellt für jeden Dokumenttyp ein Einzelansicht-Typ zugeordnet ist. In einigen Fällen ist es wünschenswert sein, Sie haben die Möglichkeit, die die aktuelle Ansicht eines Dokuments mit einer neuen Ansicht zu wechseln.

> [!TIP]
>  Zusätzliche Verfahren zum Implementieren von mehreren Ansichten für ein einzelnes Dokument finden Sie [CDocument:: AddView](../mfc/reference/cdocument-class.md#addview) und [sammeln](../overview/visual-cpp-samples.md) MFC-Beispiel.

Sie können diese Funktionalität implementieren, indem er ein neues `CView`-abgeleitete Klasse sowie zusätzlichen Code für die Ansicht dynamisch zu einer vorhandenen MFC-Anwendung zu wechseln.

Die Schritte sind wie folgt aus:

- [Ändern Sie die vorhandene Anwendungsklasse](#vcconmodifyexistingapplicationa1)

- [Erstellen Sie und ändern Sie die neue Ansichtsklasse](#vcconnewviewclassa2)

- [Erstellen und Anfügen der neuen Ansicht](#vcconattachnewviewa3)

- [Implementieren der Funktion zum Wechseln](#vcconswitchingfunctiona4)

- [Fügen Sie Unterstützung für das Wechseln der Ansicht hinzu](#vcconswitchingtheviewa5)

Im weiteren Verlauf dieses Themas wird Folgendes vorausgesetzt:

- Der Name des der `CWinApp`-abgeleitete Objekt `CMyWinApp`, und `CMyWinApp` deklariert und definiert *MYWINAPP. H* und *MYWINAPP. CPP*.

- `CNewView` Der Name der neuen `CView`-abgeleitetes Objekt, und `CNewView` deklariert und definiert *NEWVIEW. H* und *NEWVIEW. CPP*.

##  <a name="vcconmodifyexistingapplicationa1"></a> Ändern Sie die vorhandene Anwendungsklasse

Für die Anwendung zwischen Ansichten wechseln müssen Sie die Anwendungsserver-Klasse durch das Hinzufügen von Membervariablen zum Speichern von Ansichten und eine Methode zum Wechseln zu ändern.

Fügen Sie den folgenden Code zur Deklaration des `CMyWinApp` in *MYWINAPP. H*:

[!code-cpp[NVC_MFCDocViewSDI#1](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]

Die neue Membervariablen `m_pOldView` und `m_pNewView`, zeigen Sie auf die aktuelle Ansicht und der neu erstellten. Die neue Methode (`SwitchView`) wechselt die Ansichten für das vom Benutzer angefordert. Der Text der Methode wird weiter unten in diesem Thema erläutert [implementieren die Funktion wechseln](#vcconswitchingfunctiona4).

Die letzte Änderung an der Anwendungsklasse erfordert eine neue Headerdatei, die eine Windows-Nachricht definiert einschließlich (**WM_INITIALUPDATE**), die in der Funktion zum Wechseln verwendet wird.

Fügen Sie die folgende Zeile im Includeabschnitt "der *MYWINAPP. CPP*:

[!code-cpp[NVC_MFCDocViewSDI#2](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]

Die Änderungen zu speichern und mit dem nächsten Schritt fort.

##  <a name="vcconnewviewclassa2"></a> Erstellen Sie und ändern Sie die neue Ansichtsklasse

Erstellen die neue Ansichtsklasse erfolgt einfach mithilfe der **neue Klasse** Befehl in der Klassenansicht. Die einzige Voraussetzung für diese Klasse ist, dass es abgeleitet `CView`. Fügen Sie diese neue Klasse, für die Anwendung. Spezifische Informationen auf dem Projekt eine neue Klasse hinzugefügt werden, finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md).

Nachdem Sie die Klasse dem Projekt hinzugefügt haben, müssen Sie den Zugriff auf einige anzeigen-Klasse, Elemente zu ändern.

Ändern Sie *NEWVIEW. H* durch Ändern der Zugriffsspezifizierer aus **geschützt** zu **öffentliche** für den Konstruktor und Destruktor. Dadurch wird die Klasse zu erstellen und dynamisch zerstört und die Darstellung der Ansicht zu ändern, bevor es angezeigt wird.

Die Änderungen zu speichern und mit dem nächsten Schritt fort.

##  <a name="vcconattachnewviewa3"></a> Erstellen und Anfügen der neuen Ansicht

Zum Erstellen, und fügen Sie die neue Sicht, müssen Sie ändern die `InitInstance` Funktion der Anwendungsklasse. Die Änderung fügt neuen Code, der erstellt ein neues Objekt und initialisiert beide `m_pOldView` und `m_pNewView` mit den zwei vorhandene Ansicht-Objekten.

Da die neue Ansicht, innerhalb erstellt wird der `InitInstance` -Funktion, die neuen und vorhandenen Ansichten, die für die Lebensdauer der Anwendung beibehalten werden. Allerdings kann die Anwendung die neue Ansicht genauso einfach dynamisch erstellen.

Fügen Sie diesen Code nach dem Aufruf von `ProcessShellCommand`:

[!code-cpp[NVC_MFCDocViewSDI#3](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]

Die Änderungen zu speichern und mit dem nächsten Schritt fort.

##  <a name="vcconswitchingfunctiona4"></a> Implementieren der Funktion zum Wechseln

Im vorherigen Schritt haben Sie Code, der erstellt und initialisiert ein neues Objekt hinzugefügt. Der letzte wichtige Schritt ist die Implementierung von der Methode durch den Wechsel des `SwitchView`.

Am Ende der Implementierungsdatei für Ihre Anwendungsklasse (*MYWINAPP. CPP*), fügen Sie die folgende Methodendefinition hinzu:

[!code-cpp[NVC_MFCDocViewSDI#4](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]

Die Änderungen zu speichern und mit dem nächsten Schritt fort.

##  <a name="vcconswitchingtheviewa5"></a> Fügen Sie Unterstützung für das Wechseln der Ansicht hinzu

Der letzte Schritt umfasst das Hinzufügen von Code, der Aufrufe der `SwitchView` Methode, wenn die Anwendung zwischen Ansichten wechseln muss. Dies kann auf verschiedene Weise durchgeführt werden kann: indem Sie ein neues Menüelement für den Benutzer hinzufügen oder intern die Ansicht wechseln, wenn bestimmte Bedingungen erfüllt sind.

Weitere Informationen zum Hinzufügen von neuen Menüelemente sowie befehlshandlerfunktionen finden Sie unter [Handler für Befehle und Steuerelementbenachrichtigungen](../mfc/handlers-for-commands-and-control-notifications.md).

## <a name="see-also"></a>Siehe auch

[Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)
