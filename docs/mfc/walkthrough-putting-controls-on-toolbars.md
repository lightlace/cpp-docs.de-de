---
title: "Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einf&#252;gen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anpassen-Dialogfeld, Hinzufügen von Steuerelementen"
  - "Symbolleisten, Hinzufügen von Steuerelementen"
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einf&#252;gen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird das Hinzufügen einer Symbolleistenschaltfläche beschrieben, die ein Windows\-Steuerelement für eine Symbolleiste enthält.  In MFC muss eine Symbolleistenschaltfläche eine von [CMFCToolBarButton Class](../mfc/reference/cmfctoolbarbutton-class.md) abgeleitete Klasse sein, beispielsweise [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton Class](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbarButton Class](../mfc/reference/cmfcdropdowntoolbarbutton-class.md) oder [CMFCToolBarMenuButton Class](../mfc/reference/cmfctoolbarmenubutton-class.md).  
  
## Hinzufügen von Steuerelementen zu Symbolleisten  
 Führen Sie zum Hinzufügen eines Steuerelements zu einer Symbolleiste die folgenden Schritte aus:  
  
1.  Reservieren Sie eine Platzhalterressourcen\-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  Weitere Informationen über die Erstellung von Schaltflächen mithilfe des Symbolleisten\-Editors in Visual Studio finden Sie im Thema [Toolbar Editor](../mfc/toolbar-editor.md).  
  
2.  Reservieren Sie ein Symbolleistenbild \(Schaltflächensymbol\) für die Schaltfläche in allen Bitmaps der übergeordneten Symbolleiste.  
  
3.  Führen Sie im Meldungshandler, der die Meldung `AFX_WM_RESETTOOLBAR` verarbeitet, folgende Schritte aus:  
  
    1.  Erstellen Sie das Schaltflächensteuerelement mithilfe einer von `CMFCToolbarButton` abgeleiteten Klasse.  
  
    2.  Ersetzen Sie die Platzhalterschaltfläche mithilfe von [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) durch das neue Steuerelement.  Sie können das Schaltflächenobjekt auf dem Stapel erstellen, da `ReplaceButton` das Schaltflächenobjekt kopiert und die Kopie beibehält.  
  
> [!NOTE]
>  Wenn Sie die Anpassung in Ihrer Anwendung aktiviert haben, müssen Sie die Symbolleiste möglicherweise mit der Schaltfläche **Zurücksetzen** auf der Registerkarte **Symbolleisten** des Dialogfelds **Anpassen** zurücksetzen, um das aktualisierte Steuerelement nach dem erneuten Kompilieren in der Anwendung anzuzeigen.  Der Zustand der Symbolleiste wird in der Windows\-Registrierung gespeichert, und die Registrierungsinformationen werden geladen und angewendet, nachdem die `ReplaceButton`\-Methode während des Anwendungsstarts ausgeführt wurde.  
  
## Symbolleisten\-Steuerelemente und Anpassung  
 Die Registerkarte **Befehle** des Dialogfelds **Anpassen** enthält eine Liste von Befehlen, die in der Anwendung verfügbar sind.  Standardmäßig verarbeitet das Dialogfeld **Anpassen** die Anwendungsmenüs und erstellt eine Liste der Standard\-Symbolleistenschaltflächen in jeder Menükategorie.  Zur Beibehaltung der erweiterten Funktionalität, die die Symbolleisten\-Steuerelemente bieten, müssen Sie die Standard\-Symbolleistenschaltfläche durch das benutzerdefinierte Steuerelement im Dialogfeld **Anpassen** ersetzen.  
  
 Wenn Sie die Anpassung aktivieren, erstellen Sie das Dialogfeld **Anpassen** im Anpassungshandler `OnViewCustomize` mithilfe der [CMFCToolBarsCustomizeDialog Class](../mfc/reference/cmfctoolbarscustomizedialog-class.md)\-Klasse.  Bevor Sie das Dialogfeld **Anpassen** durch Aufrufen von [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md) anzeigen, rufen Sie [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md) auf, um die Standardschaltfläche durch das neue Steuerelement zu ersetzen.  
  
## Beispiel: Erstellen eines Suchkombinationsfelds  
 In diesem Abschnitt wird die Erstellung eines `Find`\-Kombinationsfeld\-Steuerelements beschrieben, das in einer Symbolleiste angezeigt wird und kürzlich verwendete Suchzeichenfolgen enthält.  Der Benutzer kann eine Zeichenfolge im Steuerelement eingeben und die EINGABETASTE drücken, um ein Dokument zu suchen, oder er kann die ESC\-TASTE drücken, um zum Hauptframe zurückzukehren.  In diesem Beispiel wird davon ausgegangen, dass das Dokument in einer von [CEditView Class](../mfc/reference/ceditview-class.md) abgeleiteten Ansicht angezeigt wird.  
  
### Erstellen des Suchen\-Steuerelements  
 Erstellen Sie zuerst das `Find`\-Kombinationsfeld\-Steuerelement:  
  
1.  Fügen Sie den Anwendungsressourcen die Schaltfläche und die zugehörigen Befehle hinzu:  
  
    1.  Fügen Sie in den Anwendungsressourcen eine neue Schaltfläche mit einer `ID_EDIT_FIND`\-Befehls\-ID zu einer Symbolleiste in Ihrer Anwendung und zu allen der Symbolleiste zugeordneten Bitmaps hinzu.  
  
    2.  Erstellen Sie ein neues Menüelement mit der Befehls\-ID ID\_EDIT\_FIND.  
  
    3.  Fügen Sie der Zeichenfolgentabelle eine neue Zeichenfolge "Text suchen\\nSuchen" hinzu, und weisen Sie ihr eine `ID_EDIT_FIND_COMBO`\-Befehls\-ID zu.  Diese ID wird als Befehls\-ID der `Find`\-Kombinationsfelds\-Schaltfläche verwendet.  
  
        > [!NOTE]
        >  Da `ID_EDIT_FIND` ein Standardbefehl ist, der von `CEditView` verarbeitet wird, ist es nicht erforderlich, einen speziellen Handler für diesen Befehl zu implementieren.  Sie müssen jedoch einen Handler für den neuen Befehl `ID_EDIT_FIND_COMBO` implementieren.  
  
2.  Erstellen Sie die neue Klasse, `CFindComboBox`, abgeleitet von [CComboBox Class](../mfc/reference/ccombobox-class.md).  
  
3.  Überschreiben Sie in der Klasse `CFindComboBox` die virtuelle Methode `PreTranslateMessage`.  Diese Methode ermöglicht dem Kombinationsfeld, die Meldung [WM\_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) zu verarbeiten.  Wenn der Benutzer die ESC\-TASTE \(`VK_ESCAPE`\) drückt, kehren Sie zum Hauptrahmenfenster zurück.  Wenn der Benutzer die EINGABETASTE \(`VK_ENTER`\) drückt, geben Sie im Hauptrahmenfenster eine `WM_COMMAND`\-Meldung aus, die die Befehls\-ID `ID_EDIT_FIND_COMBO` enthält.  
  
4.  Erstellen Sie eine Klasse für die `Find`\-Kombinationsfeldschaltfläche, abgeleitet von [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  In diesem Beispiel hat sie den Namen `CFindComboButton`.  
  
5.  Der Konstruktor von `CMFCToolbarComboBoxButton` akzeptiert drei Parameter: die Befehls\-ID der Schaltfläche, den Index des Schaltflächensymbols und das Format des Kombinationsfelds.  Legen Sie diese Parameter wie folgt fest:  
  
    1.  Übergeben Sie `ID_EDIT_FIND_COMBO` als Befehls\-ID.  
  
    2.  Verwenden Sie [CCommandManager::GetCmdImage](assetId:///4094d08e-de74-4398-a483-76d27a742dca) mit `ID_EDIT_FIND`, um den Bildindex abzurufen.  
  
    3.  Eine Liste der verfügbaren Kombinationsfeldformate finden Sie unter [Kombinationsfeldstile](../mfc/reference/combo-box-styles.md).  
  
6.  Überschreiben Sie in der `CFindComboButton`\-Klasse die `CMFCToolbarComboBoxButton::CreateCombo`\-Methode.  Hier sollten Sie das `CFindComboButton`\-Objekt erstellen und einen Zeiger darauf zurückgeben.  
  
7.  Verwenden Sie das Makro [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md), um die Kombinationsschaltfläche persistent zu erstellen.  Der Arbeitsbereichs\-Manager lädt und speichert den Zustand der Schaltfläche automatisch in der Windows\-Registrierung.  
  
8.  Implementieren Sie den `ID_EDIT_FIND_COMBO`\-Handler in der Dokumentenansicht.  Verwenden Sie [CMFCToolBar::GetCommandButtons](../Topic/CMFCToolBar::GetCommandButtons.md) mit `ID_EDIT_FIND_COMBO`, um alle `Find`\-Kombinationsfeldschaltflächen abzurufen.  Aufgrund der Anpassung können mehrere Kopien einer Schaltfläche mit derselben Befehls\-ID vorhanden sein.  
  
9. Verwenden Sie im ID\_EDIT\_FIND\-Meldungshandler `OnFind` die Klasse [CMFCToolBar::IsLastCommandFromButton](../Topic/CMFCToolBar::IsLastCommandFromButton.md), um festzustellen, ob der Suchbefehl von der `Find`\-Kombinationsfeldschaltfläche gesendet wurde.  Wenn dies der Fall ist, suchen Sie den Text, und fügen Sie dem Kombinationsfeld die Suchzeichenfolge hinzu.  
  
### Hinzufügen des Suchen\-Steuerelements zur Hauptsymbolleiste  
 Führen Sie zum Hinzufügen der Kombinationsfeldschaltfläche zur Symbolleiste die folgenden Schritte aus:  
  
1.  Implementieren Sie den `AFX_WM_RESETTOOLBAR`\-Meldungshandler `OnToolbarReset` im Hauptrahmenfenster.  
  
    > [!NOTE]
    >  Das Framework sendet diese Meldung an das Hauptrahmenfenster, wenn während des Anwendungsstarts eine Symbolleiste initialisiert wird oder wenn eine Symbolleiste während der Anpassung zurückgesetzt wird.  In beiden Fall müssen Sie die Standard\-Symbolleistenschaltfläche durch die benutzerdefinierte `Find` Kombinationsfeldschaltfläche ersetzen.  
  
2.  Überprüfen Sie im `AFX_WM_RESETTOOLBAR`\-Handler die Symbolleisten\-ID, d. h. den `WPARAM`\-Wert der `AFX_WM_RESETTOOLBAR`\-Meldung.  Wenn die Symbolleisten\-ID der der Symbolleiste entspricht, die die `Find`\-Kombinationsfeldschaltfläche enthält, rufen Sie [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) auf, um die `Find`\-Schaltfläche \(d. h. die Schaltfläche mit der Befehls\-ID `ID_EDIT_FIND)` durch ein `CFindComboButton`\-Objekt zu ersetzen.  
  
    > [!NOTE]
    >  Sie können ein `CFindComboBox`\-Objekt auf dem Stapel erstellen, da `ReplaceButton` das Schaltflächenobjekt kopiert und die Kopie beibehält.  
  
### Hinzufügen des Suchen\-Steuerelements zum Dialogfeld "Anpassen"  
 Rufen Sie im Anpassungshandler `OnViewCustomize` die Klasse [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md) auf, um die `Find`\-Schaltfläche \(d. h. die Schaltfläche mit der Befehls\-ID `ID_EDIT_FIND)` durch ein `CFindComboButton`\-Objekt zu ersetzen.  
  
## Siehe auch  
 [Hierarchiediagramm](../mfc/hierarchy-chart.md)   
 [Klassen](../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton Class](../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCToolBarsCustomizeDialog Class](../mfc/reference/cmfctoolbarscustomizedialog-class.md)