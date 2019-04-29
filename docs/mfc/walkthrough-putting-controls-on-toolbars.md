---
title: 'Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf der Symbolleiste'
ms.date: 04/25/2019
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: 0b5b8685b3062bf63187a765b7e90e26f8c65681
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392452"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf der Symbolleiste

Dieser Artikel beschreibt, wie Sie eine Symbolleisten-Schaltfläche hinzufügen, die ein Windows-Steuerelement zu einer Symbolleiste enthält. In MFC muss eine Symbolleisten-Schaltfläche einer [CMFCToolBarButton-Klasse](../mfc/reference/cmfctoolbarbutton-class.md)-abgeleitete Klasse sein, z. B. [CMFCToolBarComboBoxButton-Klasse](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton-Klasse](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbarButton-Klasse](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), oder [CMFCToolBarMenuButton-Klasse](../mfc/reference/cmfctoolbarmenubutton-class.md).

## <a name="adding-controls-to-toolbars"></a>Hinzufügen von Steuerelementen zu Symbolleisten

Führen Sie zum Hinzufügen eines Steuerelements zu einer Symbolleiste die folgenden Schritte aus:

1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource. Weitere Informationen zum Erstellen von Schaltflächen mit den **Symbolleisten-Editor** in Visual Studio finden Sie unter den [Symbolleisten-Editor](../windows/toolbar-editor.md) Artikel.

1. Reservieren Sie ein Symbolleistenbild (Schaltflächensymbol) für die Schaltfläche in allen Bitmaps der übergeordneten Symbolleiste.

1. In der Message-Handler, der verarbeitet die `AFX_WM_RESETTOOLBAR` angezeigt wird, gehen Sie folgendermaßen vor:

   1. Erstellen Sie das Schaltflächensteuerelement mithilfe einer von `CMFCToolbarButton` abgeleiteten Klasse.

   1. Ersetzen Sie die platzhalterschaltfläche mithilfe durch das neue Steuerelement [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton). Sie können das Schaltflächenobjekt auf dem Stapel erstellen, da `ReplaceButton` das Schaltflächenobjekt kopiert und die Kopie beibehält.

> [!NOTE]
>  Wenn Sie Anpassungen in Ihrer Anwendung aktiviert haben, müssen Sie möglicherweise auf die Symbolleiste mit zurückgesetzt der **zurücksetzen** auf auf die Schaltfläche der **Symbolleisten** auf der Registerkarte die **anpassen** finden im Dialogfeld die aktualisierte Steuerelement in Ihrer Anwendung nach dem erneuten Kompilieren. Der Zustand der Symbolleiste wird in der Windows-Registrierung gespeichert, und die Registrierungsinformationen werden geladen und angewendet, nachdem die `ReplaceButton`-Methode während des Anwendungsstarts ausgeführt wurde.

## <a name="toolbar-controls-and-customization"></a>Symbolleisten-Steuerelemente und Anpassung

Die **Befehle** Registerkarte die **anpassen** Dialogfeld enthält eine Liste der Befehle, die in der Anwendung verfügbar sind. In der Standardeinstellung die **anpassen** Dialogfeld verarbeitet die Anwendungsmenüs und erstellt eine Liste der standard-Symbolleistenschaltflächen in jeder Menükategorie. Um die erweiterten Funktionen zu halten, die die Symbolleisten-Steuerelemente bereitstellen, müssen Sie die standard-Symbolleistenschaltfläche durch das benutzerdefinierte Steuerelement im Ersetzen der **anpassen** Dialogfeld.

Wenn Sie die Anpassung aktivieren, erstellen Sie die **anpassen** Dialogfeld im anpassungshandler `OnViewCustomize` mithilfe der [CMFCToolBarsCustomizeDialog-Klasse](../mfc/reference/cmfctoolbarscustomizedialog-class.md) Klasse. Um Anzeigen der **anpassen** Dialogfeld durch Aufrufen von [CMFCToolBarsCustomizeDialog::Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create), rufen Sie [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) ersetzen die Standardschaltfläche durch das neue Steuerelement.

## <a name="example-creating-a-find-combo-box"></a>Beispiel: Erstellen eines Suchkombinationsfelds

Dieser Abschnitt enthält Informationen zum Erstellen einer **finden** Kombinationsfeld-Steuerelement, das auf einer Symbolleiste angezeigt wird und kürzlich verwendete Suchzeichenfolgen enthält. Der Benutzer kann eine Zeichenfolge im Steuerelement eingeben und die EINGABETASTE drücken, um ein Dokument zu suchen, oder er kann die ESC-TASTE drücken, um zum Hauptframe zurückzukehren. In diesem Beispiel wird davon ausgegangen, dass das Dokument, in angezeigt wird einem [CEditView-Klasse](../mfc/reference/ceditview-class.md)-Ansicht abgeleitet.

### <a name="creating-the-find-control"></a>Erstellen des Suchen-Steuerelements

Erstellen Sie zunächst die **finden** Kombinationsfeld-Steuerelement:

1. Fügen Sie den Anwendungsressourcen die Schaltfläche und die zugehörigen Befehle hinzu:

   1. Fügen Sie in den Anwendungsressourcen eine neue Schaltfläche mit einer `ID_EDIT_FIND`-Befehls-ID zu einer Symbolleiste in Ihrer Anwendung und zu allen der Symbolleiste zugeordneten Bitmaps hinzu.

   1. Erstellen Sie ein neues Menüelement mit der `ID_EDIT_FIND` Befehls-ID

   1. Fügen Sie der Zeichenfolgentabelle eine neue Zeichenfolge "Text suchen\nSuchen" hinzu, und weisen Sie ihr eine `ID_EDIT_FIND_COMBO`-Befehls-ID zu. Diese ID wird als Befehls-ID der verwendet die **finden** Kombinationsfelds-Schaltfläche.

        > [!NOTE]
        > Da `ID_EDIT_FIND` ein Standardbefehl ist, der von `CEditView` verarbeitet wird, ist es nicht erforderlich, einen speziellen Handler für diesen Befehl zu implementieren.  Sie müssen jedoch einen Handler für den neuen Befehl `ID_EDIT_FIND_COMBO` implementieren.

1. Erstellen Sie eine neue Klasse `CFindComboBox`, abgeleitet von [CComboBox-Klasse](../mfc/reference/ccombobox-class.md).

1. Überschreiben Sie in der Klasse `CFindComboBox` die virtuelle Methode `PreTranslateMessage`. Diese Methode ermöglicht das Kombinationsfeld zum Verarbeiten der [WM_KEYDOWN](/windows/desktop/inputdev/wm-keydown) Nachricht. Wenn der Benutzer die ESC-TASTE (`VK_ESCAPE`) drückt, kehren Sie zum Hauptrahmenfenster zurück. Wenn der Benutzer die EINGABETASTE (`VK_ENTER`) drückt, geben Sie im Hauptrahmenfenster eine `WM_COMMAND`-Meldung aus, die die Befehls-ID `ID_EDIT_FIND_COMBO` enthält.

1. Erstellen Sie eine Klasse für den **finden** kombinationsfeldschaltfläche, abgeleitet [CMFCToolBarComboBoxButton-Klasse](../mfc/reference/cmfctoolbarcomboboxbutton-class.md). In diesem Beispiel hat es den Namen `CFindComboButton`.

1. Der Konstruktor von `CMFCToolbarComboBoxButton` akzeptiert drei Parameter: die Befehls-ID der Schaltfläche, den Index des Schaltflächensymbols und das Format des Kombinationsfelds. Legen Sie diese Parameter wie folgt fest:

   1. Übergeben Sie `ID_EDIT_FIND_COMBO` als Befehls-ID.

   1. Verwendung [CCommandManager::GetCmdImage](reference/internal-classes.md) mit `ID_EDIT_FIND` der Bildindex abgerufen.

   1. Eine Liste der verfügbaren kombinationsfeldformate, finden Sie unter [Kombinationsfeldstile](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).

1. Überschreiben Sie in der `CFindComboButton`-Klasse die `CMFCToolbarComboBoxButton::CreateCombo`-Methode. Hier sollten Sie das `CFindComboButton`-Objekt erstellen und einen Zeiger darauf zurückgeben.

1. Verwenden der [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) Makro, um die Kombinationsschaltfläche persistent zu machen. Der Arbeitsbereichs-Manager lädt und speichert den Zustand der Schaltfläche automatisch in der Windows-Registrierung.

1. Implementieren Sie den `ID_EDIT_FIND_COMBO`-Handler in der Dokumentenansicht. Verwendung [CMFCToolBar::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) mit `ID_EDIT_FIND_COMBO` abzurufenden alle **finden** -kombinationsfeldschaltflächen. Aufgrund der Anpassung können mehrere Kopien einer Schaltfläche mit derselben Befehls-ID vorhanden sein.

1. In der `ID_EDIT_FIND` Meldungshandler `OnFind`, verwenden Sie [CMFCToolBar::IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) zu bestimmen, ob der Suchbefehl von gesendet wurde der **finden** Kombinationsfelds-Schaltfläche. Wenn dies der Fall ist, suchen Sie den Text, und fügen Sie dem Kombinationsfeld die Suchzeichenfolge hinzu.

### <a name="adding-the-find-control-to-the-main-toolbar"></a>Hinzufügen des Suchen-Steuerelements zur Hauptsymbolleiste

Führen Sie zum Hinzufügen der Kombinationsfeldschaltfläche zur Symbolleiste die folgenden Schritte aus:

1. Implementieren Sie den `AFX_WM_RESETTOOLBAR`-Meldungshandler `OnToolbarReset` im Hauptrahmenfenster.

    > [!NOTE]
    > Das Framework sendet diese Meldung an das Hauptrahmenfenster, wenn während des Anwendungsstarts eine Symbolleiste initialisiert wird oder wenn eine Symbolleiste während der Anpassung zurückgesetzt wird. In beiden Fällen müssen Sie die standard-Symbolleistenschaltfläche ersetzen, mit dem benutzerdefinierten **finden** Kombinationsfelds-Schaltfläche.

1. In der `AFX_WM_RESETTOOLBAR` Handler auf, untersuchen Sie die Symbolleisten-ID, d. h., die *WPARAM* der AFX_WM_RESETTOOLBAR Nachricht. Wenn die Symbolleisten-ID entspricht, der Symbolleiste ist, enthält die **finden** kombinationsfeldschaltfläche, rufen [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton) ersetzen die **finden** Schaltfläche (, also die Schaltfläche mit den Befehls-ID `ID_EDIT_FIND)` mit einem `CFindComboButton` Objekt.

    > [!NOTE]
    > Sie können ein `CFindComboBox`-Objekt auf dem Stapel erstellen, da `ReplaceButton` das Schaltflächenobjekt kopiert und die Kopie beibehält.

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Hinzufügen des Suchen-Steuerelements zum Dialogfeld "Anpassen"

Im anpassungshandler `OnViewCustomize`, rufen Sie [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) ersetzen die **finden** Schaltfläche (d. h. die Schaltfläche mit den Befehls-ID `ID_EDIT_FIND`) mit einem `CFindComboButton` Objekt.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../mfc/hierarchy-chart.md)<br/>
[Klassen](../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar-Klasse](../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton-Klasse](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton-Klasse](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCToolBarsCustomizeDialog-Klasse](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
