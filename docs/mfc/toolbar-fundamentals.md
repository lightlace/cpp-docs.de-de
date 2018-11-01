---
title: Grundlegendes über Symbolleisten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- RT_TOOLBAR
dev_langs:
- C++
helpviewer_keywords:
- embedding toolbar in frame window class [MFC]
- application wizards [MFC], installing default application toolbars
- toolbars [MFC], creating
- resources [MFC], toolbar
- toolbar controls [MFC], toolbars created using Application Wizard
- toolbar controls [MFC], command ID
- RT_TOOLBAR resource [MFC]
- toolbars [MFC], adding default using Application Wizard
- LoadBitmap method [MFC], toolbars
- Toolbar editor [MFC], Application Wizard
- command IDs [MFC], toolbar buttons
- SetButtons method [MFC]
- CToolBar class [MFC], default toolbars in Application Wizard
- frame window classes [MFC], toolbar embedded in
- LoadToolBar method [MFC]
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f52c5af48631a1441b160a9b59a987f697fdedc6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438144"
---
# <a name="toolbar-fundamentals"></a>Grundlegendes über Symbolleisten

Dieser Artikel beschreibt die grundlegende MFC-Implementierung, die Ihre Anwendung eine Standardsymbolleiste hinzufügen, indem Sie im Anwendungs-Assistenten die Option ermöglicht. Zu den behandelten Themen gehören:

- [Die Option der Anwendungs-Assistent-Symbolleiste](#_core_the_appwizard_toolbar_option)

- [Die Symbolleiste im code](#_core_the_toolbar_in_code)

- [Bearbeiten die Symbolleistenressource](#_core_editing_the_toolbar_resource)

- [Mehrere Symbolleisten](#_core_multiple_toolbars)

##  <a name="_core_the_appwizard_toolbar_option"></a> Die Anwendung Assistenten-Option-Symbolleiste

Um eine einzige Symbolleiste mit Schaltflächen zu erhalten, wählen Sie die Symbolleistenoption standardmäßiges Andocken auf der Seite mit der Bezeichnung Features der Benutzeroberfläche. Dadurch wird Ihre Anwendung Code hinzugefügt, die:

- Erstellt das Symbolleistenobjekt.

- Verwaltet die Symbolleiste, einschließlich der Möglichkeit, andocken oder auf "float".

##  <a name="_core_the_toolbar_in_code"></a> Die Symbolleiste im Code

Die Symbolleiste ist eine [CToolBar](../mfc/reference/ctoolbar-class.md) Objekt deklariert als Datenmember von der Anwendung `CMainFrame` Klasse. Das heißt, wird die Toolbar-Objekt in das Hauptrahmenfenster-Objekt eingebettet. Dies bedeutet, dass MFC die Symbolleiste erstellt, wenn das Rahmenfenster erstellt und zerstört wird, wenn es sich um das Rahmenfenster zerstört. Die folgende Deklaration der partiellen Klasse, für eine Anwendung multiple Document Interface (MDI), zeigt die Datenelemente für eine eingebettete Symbolleiste und einer eingebetteten Statusleiste. Außerdem wird gezeigt, überschreiben die `OnCreate` Member-Funktion.

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

Symbolleiste-Erstellung erfolgt in `CMainFrame::OnCreate`. MFC-Aufrufe [OnCreate](../mfc/reference/cwnd-class.md#oncreate) nach dem Erstellen des Fensters für den Frame, aber bevor er angezeigt wird. Der Standardwert `OnCreate` , der Anwendungs-Assistent generiert führt Sie die folgenden Aufgaben für die Symbolleiste:

1. Ruft die `CToolBar` des Objekts [erstellen](../mfc/reference/ctoolbar-class.md#create) Member-Funktion zum Erstellen der zugrunde liegende [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Objekt.

1. Aufrufe [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) die Symbolleisteninformationen zu laden.

1. Ruft die Funktionen, um andocken, Gleitkommatyp und QuickInfos zu ermöglichen. Weitere Informationen über diese Aufrufe, finden Sie im Artikel [andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md).

> [!NOTE]
>  Im allgemeinen MFC-Beispiel [DOCKTOOL](../visual-cpp-samples.md) enthält Abbildungen der alten und neuen MFC-Symbolleisten. Die Symbolleisten, mit denen `COldToolbar` erfordern Aufrufe in Schritt 2 `LoadBitmap` (statt `LoadToolBar`) und `SetButtons`. Die neuen Symbolleisten sind Aufrufe von `LoadToolBar`.

Das Andocken, Gleitkommatyp und Aufrufe der Tool-Tipps sind optional. Sie können die Zeilen aus entfernen `OnCreate` Falls gewünscht. Das Ergebnis ist eine Symbolleiste, die feste, nicht "float" oder Redock und kann nicht angezeigt werden QuickInfos bleibt.

##  <a name="_core_editing_the_toolbar_resource"></a> Bearbeiten die Symbolleistenressource

Die Standardsymbolleiste Sie mit dem Assistenten für die Anwendung erhalten basiert auf einer **RT_TOOLBAR** benutzerdefinierte Ressource, die in MFC, Version 4.0 eingeführt wurden. Sie können diese Ressource mit dem Bearbeiten der [Symbolleisten-Editor](../windows/toolbar-editor.md). Der Editor können Sie problemlos hinzufügen, löschen und Neuanordnen von Schaltflächen. Sie enthält einen grafischen Editor für die Schaltflächen, die den allgemeine Grafikeditor in Visual C++ sehr ähnlich ist. Wenn Sie Symbolleisten in früheren Versionen von Visual C++ bearbeitet haben, finden die Aufgabe viel einfacher jetzt Sie.

Um eine Symbolleisten-Schaltfläche mit einem Befehl zu verbinden, Sie geben Ihnen der Schaltfläche eine Befehls-ID, z. B. `ID_MYCOMMAND`. Geben Sie die Befehls-ID der Schaltfläche auf der Seite in der Symbolleisten-Editor ein. Erstellen Sie dann eine Handlerfunktion für den Befehl (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md) Informationen).

Neue [CToolBar](../mfc/reference/ctoolbar-class.md) Memberfunktionen arbeiten mit der **RT_TOOLBAR** Ressource. [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) jetzt nimmt den Platz von [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) beim Laden der Bitmap des der Symbolleisten-Schaltflächen und [SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons) legen Sie das Button-Stile und Schaltflächen mit Bitmapbildern verbinden.

Weitere Informationen zur Verwendung des Symbolleisten-Editors finden Sie unter [Symbolleisten-Editor](../windows/toolbar-editor.md).

##  <a name="_core_multiple_toolbars"></a> Mehrere Symbolleisten

Der Anwendungs-Assistent bietet eine Standardsymbolleiste. Wenn Sie mehr als eine Symbolleiste in Ihrer Anwendung benötigen, können Sie Ihren Code für die zusätzlichen Symbolleisten, die basierend auf dem vom Assistenten generierten Code für die Standardsymbolleiste modellieren.

Wenn Sie eine Symbolleiste als Ergebnis eines Befehls anzeigen möchten, müssen Sie:

- Erstellen Sie eine neue Symbolleistenressource über die Symbolleiste des Editors und Laden Sie es in `OnCreate` mit der [LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) Member-Funktion.

- Betten Sie ein neues [CToolBar](../mfc/reference/ctoolbar-class.md) Objekt in die Hauptframe-Fensterklasse.

- Stellen Sie die entsprechende Funktion aufgerufen wird, in `OnCreate` andocken oder "float" der Symbolleiste, legen Sie die Formate und so weiter.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Implementieren der MFC-Symbolleiste (Übersicht die Übersichtsinformationen auf der Symbolleiste)](../mfc/mfc-toolbar-implementation.md)

- [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md)

- [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md)

- Die [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Klassen

- [Arbeiten mit dem Symbolleisten-Steuerelement](../mfc/working-with-the-toolbar-control.md)

- [Verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Siehe auch

[Implementieren der MFC-Symbolleiste](../mfc/mfc-toolbar-implementation.md)

