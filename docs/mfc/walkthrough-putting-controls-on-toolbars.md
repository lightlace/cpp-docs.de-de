---
title: 'Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c134431500ed3e7b2b2229ea5b4b3da7cac6fa48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen
In diesem Thema wird das Hinzufügen einer Symbolleistenschaltfläche beschrieben, die ein Windows-Steuerelement für eine Symbolleiste enthält. In MFC, eine Symbolleisten-Schaltfläche muss eine [CMFCToolBarButton Klasse](../mfc/reference/cmfctoolbarbutton-class.md)-abgeleitete Klasse, z. B. [CMFCToolBarComboBoxButton Klasse](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton Klasse](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbarButton Klasse](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), oder [CMFCToolBarMenuButton Klasse](../mfc/reference/cmfctoolbarmenubutton-class.md).  
  
## <a name="adding-controls-to-toolbars"></a>Hinzufügen von Steuerelementen zu Symbolleisten  
 Führen Sie zum Hinzufügen eines Steuerelements zu einer Symbolleiste die folgenden Schritte aus:  
  
1.  Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource. Weitere Informationen zum Erstellen von Schaltflächen mit der Symbolleisten-Editor in Visual Studio finden Sie unter der [Symbolleisten-Editor](../windows/toolbar-editor.md) Thema.  
  
2.  Reservieren Sie ein Symbolleistenbild (Schaltflächensymbol) für die Schaltfläche in allen Bitmaps der übergeordneten Symbolleiste.  
  
3.  Führen Sie im Meldungshandler, der die Meldung `AFX_WM_RESETTOOLBAR` verarbeitet, folgende Schritte aus:  
  
    1.  Erstellen Sie das Schaltflächensteuerelement mithilfe einer von `CMFCToolbarButton` abgeleiteten Klasse.  
  
    2.  Ersetzen Sie die Schaltfläche "dummy" durch das neue Steuerelement mit [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton). Sie können das Schaltflächenobjekt auf dem Stapel erstellen, da `ReplaceButton` das Schaltflächenobjekt kopiert und die Kopie beibehält.  
  
> [!NOTE]
>  Wenn Sie die Anpassung in Ihrer Anwendung aktiviert, müssen Sie möglicherweise mithilfe die Symbolleiste Zurücksetzen der **zurücksetzen** auf die Schaltfläche der **Symbolleisten** auf der Registerkarte die **anpassen** finden im Dialogfeld die aktualisierte Steuerelement in der Anwendung nach dem erneuten Kompilieren. Der Zustand der Symbolleiste wird in der Windows-Registrierung gespeichert, und die Registrierungsinformationen werden geladen und angewendet, nachdem die `ReplaceButton`-Methode während des Anwendungsstarts ausgeführt wurde.  
  
## <a name="toolbar-controls-and-customization"></a>Symbolleisten-Steuerelemente und Anpassung  
 Die **Befehle** auf der Registerkarte die **anpassen** Dialogfeld enthält eine Liste der Befehle, die in der Anwendung verfügbar sind. Wird standardmäßig die **anpassen** Dialogfeld verarbeitet die Anwendungsmenüs und erstellt eine Liste der standard-Symbolleistenschaltflächen in jeder Menükategorie. Um die erweiterten Funktionen beizubehalten, die die Symbolleisten-Steuerelemente bereitstellen, müssen Sie die standard-Symbolleistenschaltfläche durch das benutzerdefinierte Steuerelement im Ersetzen der **anpassen** (Dialogfeld).  
  
 Bei der Anpassung zu aktivieren, erstellen Sie die **anpassen** Dialogfeld in der Anpassung Handler `OnViewCustomize` mithilfe der [CMFCToolBarsCustomizeDialog Klasse](../mfc/reference/cmfctoolbarscustomizedialog-class.md) Klasse. Bevor Sie Anzeigen der **anpassen** Dialogfeld durch Aufrufen [CMFCToolBarsCustomizeDialog::Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create), rufen Sie [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) ersetzen die Standardschaltfläche mit dem neuen Steuerelement.  
  
## <a name="example-creating-a-find-combo-box"></a>Beispiel: Erstellen eines Suchkombinationsfelds  
 In diesem Abschnitt wird die Erstellung eines `Find`-Kombinationsfeld-Steuerelements beschrieben, das in einer Symbolleiste angezeigt wird und kürzlich verwendete Suchzeichenfolgen enthält. Der Benutzer kann eine Zeichenfolge im Steuerelement eingeben und die EINGABETASTE drücken, um ein Dokument zu suchen, oder er kann die ESC-TASTE drücken, um zum Hauptframe zurückzukehren. In diesem Beispiel wird davon ausgegangen, dass das Dokument, in angezeigt wird einem [CEditView Klasse](../mfc/reference/ceditview-class.md)-Sicht abgeleitet.  
  
### <a name="creating-the-find-control"></a>Erstellen des Suchen-Steuerelements  
 Erstellen Sie zuerst das `Find`-Kombinationsfeld-Steuerelement:  
  
1.  Fügen Sie den Anwendungsressourcen die Schaltfläche und die zugehörigen Befehle hinzu:  
  
    1.  Fügen Sie in den Anwendungsressourcen eine neue Schaltfläche mit einer `ID_EDIT_FIND`-Befehls-ID zu einer Symbolleiste in Ihrer Anwendung und zu allen der Symbolleiste zugeordneten Bitmaps hinzu.  
  
    2.  Erstellen Sie ein neues Menüelement mit der Befehls-ID ID_EDIT_FIND.  
  
    3.  Fügen Sie der Zeichenfolgentabelle eine neue Zeichenfolge "Text suchen\nSuchen" hinzu, und weisen Sie ihr eine `ID_EDIT_FIND_COMBO`-Befehls-ID zu. Diese ID wird als Befehls-ID der `Find`-Kombinationsfelds-Schaltfläche verwendet.  
  
        > [!NOTE]
        >  Da `ID_EDIT_FIND` ein Standardbefehl ist, der von `CEditView` verarbeitet wird, ist es nicht erforderlich, einen speziellen Handler für diesen Befehl zu implementieren.  Sie müssen jedoch einen Handler für den neuen Befehl `ID_EDIT_FIND_COMBO` implementieren.  
  
2.  Erstellen Sie eine neue Klasse `CFindComboBox`, abgeleitet von [CComboBox-Klasse](../mfc/reference/ccombobox-class.md).  
  
3.  Überschreiben Sie in der Klasse `CFindComboBox` die virtuelle Methode `PreTranslateMessage`. Diese Methode ermöglicht das Kombinationsfeld zum Verarbeiten der [WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) Nachricht. Wenn der Benutzer die ESC-TASTE (`VK_ESCAPE`) drückt, kehren Sie zum Hauptrahmenfenster zurück. Wenn der Benutzer die EINGABETASTE (`VK_ENTER`) drückt, geben Sie im Hauptrahmenfenster eine `WM_COMMAND`-Meldung aus, die die Befehls-ID `ID_EDIT_FIND_COMBO` enthält.  
  
4.  Erstellen Sie eine Klasse für die `Find` kombinationsfeldschaltfläche abgeleitet [CMFCToolBarComboBoxButton Klasse](../mfc/reference/cmfctoolbarcomboboxbutton-class.md). In diesem Beispiel hat sie den Namen `CFindComboButton`.  
  
5.  Der Konstruktor von `CMFCToolbarComboBoxButton` akzeptiert drei Parameter: die Befehls-ID der Schaltfläche, den Index des Schaltflächensymbols und das Format des Kombinationsfelds. Legen Sie diese Parameter wie folgt fest:  
  
    1.  Übergeben Sie `ID_EDIT_FIND_COMBO` als Befehls-ID.  
  
    2.  Verwendung [CCommandManager::GetCmdImage](http://msdn.microsoft.com/en-us/4094d08e-de74-4398-a483-76d27a742dca) mit `ID_EDIT_FIND` zum Abrufen der Image-Index.  
  
    3.  Eine Liste der verfügbaren Kombinationsfeld Feld Formatvorlagen, finden Sie unter [Kombinationsfeldstile](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).  
  
6.  Überschreiben Sie in der `CFindComboButton`-Klasse die `CMFCToolbarComboBoxButton::CreateCombo`-Methode. Hier sollten Sie das `CFindComboButton`-Objekt erstellen und einen Zeiger darauf zurückgeben.  
  
7.  Verwenden der [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) Makro auf die Schaltfläche "Kombinationsfeld" dauerhaft zu machen. Der Arbeitsbereichs-Manager lädt und speichert den Zustand der Schaltfläche automatisch in der Windows-Registrierung.  
  
8.  Implementieren Sie den `ID_EDIT_FIND_COMBO`-Handler in der Dokumentenansicht. Verwendung [CMFCToolBar::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) mit `ID_EDIT_FIND_COMBO` abzurufenden alle `Find` Schaltflächen. Aufgrund der Anpassung können mehrere Kopien einer Schaltfläche mit derselben Befehls-ID vorhanden sein.  
  
9. ID_EDIT_FIND-Nachrichtenhandler `OnFind`, verwenden Sie [CMFCToolBar::IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) zu bestimmen, ob es sich bei der Suchbefehl von gesendet wurde die `Find` Kombinationsfelds-Schaltfläche. Wenn dies der Fall ist, suchen Sie den Text, und fügen Sie dem Kombinationsfeld die Suchzeichenfolge hinzu.  
  
### <a name="adding-the-find-control-to-the-main-toolbar"></a>Hinzufügen des Suchen-Steuerelements zur Hauptsymbolleiste  
 Führen Sie zum Hinzufügen der Kombinationsfeldschaltfläche zur Symbolleiste die folgenden Schritte aus:  
  
1.  Implementieren Sie den `AFX_WM_RESETTOOLBAR`-Meldungshandler `OnToolbarReset` im Hauptrahmenfenster.  
  
    > [!NOTE]
    >  Das Framework sendet diese Meldung an das Hauptrahmenfenster, wenn während des Anwendungsstarts eine Symbolleiste initialisiert wird oder wenn eine Symbolleiste während der Anpassung zurückgesetzt wird. In beiden Fall müssen Sie die Standard-Symbolleistenschaltfläche durch die benutzerdefinierte `Find` Kombinationsfeldschaltfläche ersetzen.  
  
2.  Überprüfen Sie im `AFX_WM_RESETTOOLBAR`-Handler die Symbolleisten-ID, d. h. den `WPARAM`-Wert der `AFX_WM_RESETTOOLBAR`-Meldung. Wenn die Symbolleisten-ID, die der Symbolleiste gleich ist, enthält die `Find` kombinationsfeldschaltfläche, rufen [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton) ersetzen die `Find` Schaltfläche (also auf die Schaltfläche mit den Befehls-ID `ID_EDIT_FIND)` mit einer `CFindComboButton` Objekt.  
  
    > [!NOTE]
    >  Sie können ein `CFindComboBox`-Objekt auf dem Stapel erstellen, da `ReplaceButton` das Schaltflächenobjekt kopiert und die Kopie beibehält.  
  
### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Hinzufügen des Suchen-Steuerelements zum Dialogfeld "Anpassen"  
 Im Handler Anpassung `OnViewCustomize`, Aufrufen [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) ersetzen die `Find` Schaltfläche (d. h. auf die Schaltfläche mit den Befehls-ID `ID_EDIT_FIND)` mit eine `CFindComboButton` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../mfc/hierarchy-chart.md)   
 [Klassen](../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton-Klasse](../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton-Klasse](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCToolBarsCustomizeDialog-Klasse](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
