---
title: 'Exemplarische Vorgehensweise: Einfügen von Steuerelementen in Symbolleisten'
ms.date: 04/25/2019
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: 0c62a8b484cb666427f873244221afec5d4719da
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510738"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>Exemplarische Vorgehensweise: Einfügen von Steuerelementen in Symbolleisten

In diesem Artikel wird beschrieben, wie eine Symbolleisten-Schaltfläche hinzugefügt wird, die ein Windows-Steuerelement enthält. In MFC muss eine Symbolleisten Schaltfläche eine von der Klasse abgeleitete [cmfctoolbarbutton](../mfc/reference/cmfctoolbarbutton-class.md)-Klasse sein, z. b. [cmfctoolbarcomboboxbutton-Klasse](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [cmfctoolbareditboxbutton-Klasse](../mfc/reference/cmfctoolbareditboxbutton-class.md), [cmfcdropdowntoolbarbutton-Klasse](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), oder [ Cmfctoolbarmenubutton-Klasse](../mfc/reference/cmfctoolbarmenubutton-class.md).

## <a name="adding-controls-to-toolbars"></a>Hinzufügen von Steuerelementen zu Symbolleisten

Führen Sie zum Hinzufügen eines Steuerelements zu einer Symbolleiste die folgenden Schritte aus:

1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource. Weitere Informationen zum Erstellen von Schaltflächen mithilfe des Symbolleisten- **Editors** in Visual Studio finden Sie im Artikel Symbolleisten- [Editor](../windows/toolbar-editor.md) .

1. Reservieren Sie ein Symbolleistenbild (Schaltflächensymbol) für die Schaltfläche in allen Bitmaps der übergeordneten Symbolleiste.

1. Führen Sie im Meldungs Handler, `AFX_WM_RESETTOOLBAR` der die Nachricht verarbeitet, die folgenden Schritte aus:

   1. Erstellen Sie das Schaltflächensteuerelement mithilfe einer von `CMFCToolbarButton` abgeleiteten Klasse.

   1. Ersetzen Sie die dummyschaltfläche durch das neue Steuerelement mithilfe von [cmfctoolbar:: replacebutton](../mfc/reference/cmfctoolbar-class.md#replacebutton). Sie können das Schaltflächenobjekt auf dem Stapel erstellen, da `ReplaceButton` das Schaltflächenobjekt kopiert und die Kopie beibehält.

> [!NOTE]
>  Wenn Sie die Anpassung in der Anwendung aktiviert haben, müssen Sie möglicherweise die Symbolleiste mithilfe der Schaltfläche **Zurücksetzen** auf der Registerkarte **Symbolleisten** des Dialog Felds **Anpassen** zurücksetzen, um nach der erneuten Kompilierung das aktualisierte Steuerelement in der Anwendung anzuzeigen. Der Zustand der Symbolleiste wird in der Windows-Registrierung gespeichert, und die Registrierungsinformationen werden geladen und angewendet, nachdem die `ReplaceButton`-Methode während des Anwendungsstarts ausgeführt wurde.

## <a name="toolbar-controls-and-customization"></a>Symbolleisten-Steuerelemente und Anpassung

Die Registerkarte **Befehle** im Dialogfeld **Anpassen** enthält eine Liste der Befehle, die in der Anwendung verfügbar sind. Standardmäßig werden die Anwendungs Menüs im Dialogfeld **Anpassen** verarbeitet, und in jeder Menükategorie wird eine Liste mit Standard Schaltflächen für die Symbolleiste erstellt. Um die erweiterten Funktionen beizubehalten, die die Symbolleisten-Steuerelemente bereitstellen, müssen Sie die Standard-Symbolleisten Schaltfläche durch das benutzerdefinierte Steuerelement im Dialogfeld **Anpassen** ersetzen.

Wenn Sie die Anpassung aktivieren, erstellen Sie das Dialogfeld **Anpassen** im Anpassungs Handler `OnViewCustomize` mithilfe der [cmfctoolbarscustomizedialog Class](../mfc/reference/cmfctoolbarscustomizedialog-class.md) -Klasse. Bevor Sie das Dialogfeld **Anpassen** anzeigen, indem Sie [cmfctoolbarscustomizedialog:: Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create)aufrufen, rufen Sie [cmfctoolbarscustomizedialog:: replacebutton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) auf, um die Standard Schaltfläche durch das neue Steuerelement zu ersetzen.

## <a name="example-creating-a-find-combo-box"></a>Beispiel: Erstellen eines Kombinations Felds ' suchen '

In diesem Abschnitt wird beschrieben, wie Sie ein Kombinations Feld-Steuerelement **Suchen** erstellen, das auf einer Symbolleiste angezeigt wird und zuletzt verwendete Such Zeichenfolgen enthält. Der Benutzer kann eine Zeichenfolge im Steuerelement eingeben und die EINGABETASTE drücken, um ein Dokument zu suchen, oder er kann die ESC-TASTE drücken, um zum Hauptframe zurückzukehren. In diesem Beispiel wird davon ausgegangen, dass das Dokument in einer von der [CEditView-Klasse](../mfc/reference/ceditview-class.md)abgeleiteten Ansicht angezeigt wird.

### <a name="creating-the-find-control"></a>Erstellen des Suchen-Steuerelements

Erstellen Sie zuerst das Kontrollkästchen Kombinations Feld **Suchen** :

1. Fügen Sie den Anwendungsressourcen die Schaltfläche und die zugehörigen Befehle hinzu:

   1. Fügen Sie in den Anwendungsressourcen eine neue Schaltfläche mit einer `ID_EDIT_FIND`-Befehls-ID zu einer Symbolleiste in Ihrer Anwendung und zu allen der Symbolleiste zugeordneten Bitmaps hinzu.

   1. Erstellen Sie ein neues Menü Element mit `ID_EDIT_FIND` der Befehls-ID.

   1. Fügen Sie der Zeichenfolgentabelle eine neue Zeichenfolge "Text suchen\nSuchen" hinzu, und weisen Sie ihr eine `ID_EDIT_FIND_COMBO`-Befehls-ID zu. Diese ID wird als Befehls-ID der Schaltfläche Kombinations Feld **Suchen** verwendet.

        > [!NOTE]
        > Da `ID_EDIT_FIND` ein Standardbefehl ist, der von `CEditView` verarbeitet wird, ist es nicht erforderlich, einen speziellen Handler für diesen Befehl zu implementieren.  Sie müssen jedoch einen Handler für den neuen Befehl `ID_EDIT_FIND_COMBO` implementieren.

1. Erstellen Sie eine neue Klasse `CFindComboBox`,, die von der [CComboBox-Klasse](../mfc/reference/ccombobox-class.md)abgeleitet wird.

1. Überschreiben Sie in der Klasse `CFindComboBox` die virtuelle Methode `PreTranslateMessage`. Diese Methode aktiviert das Kombinations Feld, um die [WM_KEYDOWN](/windows/win32/inputdev/wm-keydown) -Nachricht zu verarbeiten. Wenn der Benutzer die ESC-TASTE (`VK_ESCAPE`) drückt, kehren Sie zum Hauptrahmenfenster zurück. Wenn der Benutzer die EINGABETASTE (`VK_ENTER`) drückt, geben Sie im Hauptrahmenfenster eine `WM_COMMAND`-Meldung aus, die die Befehls-ID `ID_EDIT_FIND_COMBO` enthält.

1. Erstellen Sie eine Klasse für die Schaltfläche Kombinations Feld **Suchen** , die von der [cmfctoolbarcomboboxbutton-Klasse](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)abgeleitet wurde. In diesem Beispiel hat es den Namen `CFindComboButton`.

1. Der Konstruktor von `CMFCToolbarComboBoxButton` akzeptiert drei Parameter: die Befehls-ID der Schaltfläche, den Index des Schaltflächensymbols und das Format des Kombinationsfelds. Legen Sie diese Parameter wie folgt fest:

   1. Übergeben Sie `ID_EDIT_FIND_COMBO` als Befehls-ID.

   1. Verwenden Sie [ccommandmanager:: getcmdimage](reference/internal-classes.md) mit `ID_EDIT_FIND` , um den Bildindex abzurufen.

   1. Eine Liste der verfügbaren Kombinations Feld Stile finden Sie unter Kombinations [Feld-Stile](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).

1. Überschreiben Sie in der `CFindComboButton`-Klasse die `CMFCToolbarComboBoxButton::CreateCombo`-Methode. Hier sollten Sie das `CFindComboButton`-Objekt erstellen und einen Zeiger darauf zurückgeben.

1. Verwenden Sie das [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) -Makro, um das Kombinations Feld persistent zu machen. Der Arbeitsbereichs-Manager lädt und speichert den Zustand der Schaltfläche automatisch in der Windows-Registrierung.

1. Implementieren Sie den `ID_EDIT_FIND_COMBO`-Handler in der Dokumentenansicht. Verwenden Sie [cmfctoolbar:: getcommandbuttons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) mit `ID_EDIT_FIND_COMBO` , um alle Kombinations Feld-Schaltflächen für **Suchen** abzurufen. Aufgrund der Anpassung können mehrere Kopien einer Schaltfläche mit derselben Befehls-ID vorhanden sein.

1. Verwenden Sie `OnFind` im `ID_EDIT_FIND` Nachrichten Handler [cmfctoolbar:: islastcommandfrombutton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) , um zu bestimmen, ob der Suchbefehl von der Schaltfläche Kombinations Feld Suchen gesendet wurde. Wenn dies der Fall ist, suchen Sie den Text, und fügen Sie dem Kombinationsfeld die Suchzeichenfolge hinzu.

### <a name="adding-the-find-control-to-the-main-toolbar"></a>Hinzufügen des Suchen-Steuerelements zur Hauptsymbolleiste

Führen Sie zum Hinzufügen der Kombinationsfeldschaltfläche zur Symbolleiste die folgenden Schritte aus:

1. Implementieren Sie den `AFX_WM_RESETTOOLBAR`-Meldungshandler `OnToolbarReset` im Hauptrahmenfenster.

    > [!NOTE]
    > Das Framework sendet diese Meldung an das Hauptrahmenfenster, wenn während des Anwendungsstarts eine Symbolleiste initialisiert wird oder wenn eine Symbolleiste während der Anpassung zurückgesetzt wird. In beiden Fällen müssen Sie die Standard-Symbolleisten Schaltfläche durch die Schaltfläche benutzerdefiniertes Kombinations Feld **Suchen** ersetzen.

1. Überprüfen Sie im- HandlerdieSymbolleisten-ID,d.h.denwParam-WertderAFX_WM_RESETTOOLBAR-`AFX_WM_RESETTOOLBAR` Nachricht. Wenn die Symbolleisten-ID mit der Symbolleiste identisch ist, die die Schaltfläche Kombinations Feld **Suchen** enthält, wird [cmfctoolbar:: replacebutton](../mfc/reference/cmfctoolbar-class.md#replacebutton) aufgerufen, um die Schaltfläche **Suchen** (d. h. `ID_EDIT_FIND)` die Schalt `CFindComboButton` Fläche mit der Befehls-ID durch ein-Objekt) zu ersetzen.

    > [!NOTE]
    > Sie können ein `CFindComboBox`-Objekt auf dem Stapel erstellen, da `ReplaceButton` das Schaltflächenobjekt kopiert und die Kopie beibehält.

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Hinzufügen des Suchen-Steuerelements zum Dialogfeld "Anpassen"

`OnViewCustomize`Im Anpassungs Handler können Sie [cmfctoolbarscustomizedialog:: replacebutton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) aufrufen, um die Schaltfläche **Suchen** (d. h. die Schaltfläche mit `ID_EDIT_FIND`der Befehls- `CFindComboButton` ID) durch ein-Objekt zu ersetzen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../mfc/hierarchy-chart.md)<br/>
[Klassen](../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar-Klasse](../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton-Klasse](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton-Klasse](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCToolBarsCustomizeDialog-Klasse](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
