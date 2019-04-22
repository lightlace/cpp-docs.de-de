---
title: 'Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 2)'
ms.date: 09/20/2018
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
ms.openlocfilehash: c22a11c54b1957c1d4ac735fe8cb577d9c483d35
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781704"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 2)

[Teil 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) dieser exemplarischen Vorgehensweise wurde gezeigt, wie Sie ein Office Fluent-Multifunktionsleiste klassischen hinzufügen Scribble-Anwendung. Dieser Teil zeigt das Hinzufügen von menübandbereichen und Steuerelementen, die Benutzer anstelle von Menüs und Befehlen verwenden können.

## <a name="prerequisites"></a>Vorraussetzungen

[Visual C++-Beispiele](../overview/visual-cpp-samples.md)

##  <a name="top"></a> Abschnitte

Dieser Teil der exemplarischen Vorgehensweise enthält die folgenden Abschnitte:

- [Hinzufügen neuer Bereiche zum Menüband](#addnewpanel)

- [Hinzufügen eines Panels Hilfe zum Menüband](#addhelppanel)

- [Hinzufügen eines Stift-Panels zum Menüband](#addpenpanel)

- [Hinzufügen einer Schaltfläche "Farbe" zum Menüband](#addcolorbutton)

- [Hinzufügen eines Color-Members zur Dokumentklasse](#addcolormember)

- [Initialisieren die Stifte, und Speichern von Einstellungen](#initpensave)

##  <a name="addnewpanel"></a> Hinzufügen neuer Bereiche zum Menüband

Diese Schritte zeigen, wie Sie das Hinzufügen einer **anzeigen** Bereich, der zwei Kontrollkästchen enthält, die die Sichtbarkeit der Symbolleiste und der Statusleiste zu steuern sowie eine **Fenster** Bereich, der einem vertikal ausgerichteten Teilen enthält Schaltfläche, die das Erstellen und die Anordnung von Multiple Document Interface (MDI) Windows gesteuert.

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>Um einen Bereich und Fenster-Bereich der menübandleiste hinzugefügt werden

1. Erstellen Sie einen Bereich mit dem Namen `View`, das hat zwei Kontrollkästchen, das die Statusleiste und die Symbolleiste zu wechseln.

   1. Von der **Toolbox**, ziehen Sie eine **Bereich** auf die **Startseite** Kategorie. Ziehen Sie zwei **Kontrollkästchen** den Zugriffsbereich.

   1. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** zu `View`.

   1. Klicken Sie auf das erste Kontrollkästchen, um seine Eigenschaften zu ändern. Änderung **ID** zu `ID_VIEW_TOOLBAR` und **Beschriftung** zu `Toolbar`.

   1. Klicken Sie auf das zweite Kontrollkästchen, um seine Eigenschaften zu ändern. Änderung **ID** zu `ID_VIEW_STATUS_BAR` und **Beschriftung** zu `Status Bar`.

1. Erstellen Sie einen Bereich mit dem Namen `Window` , die eine unterteilte Schaltfläche verfügt. Wenn ein Benutzer die unterteilte Schaltfläche klickt, zeigt ein Kontextmenü drei Befehle, die bereits in der Scribble-Anwendung definiert sind.

   1. Von der **Toolbox**, ziehen Sie eine **Bereich** auf die **Startseite** Kategorie. Ziehen Sie dann eine **Schaltfläche** den Zugriffsbereich.

   1. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** zu `Window`.

   1. Klicken Sie auf die Schaltfläche. Änderung **Beschriftung** zu `Windows`, **Schlüssel** zu `w`, **Large Image Index** zu `1`, und **Teilen Modus** um `False`. Klicken Sie dann auf die Auslassungspunkte (**...** ) neben **Menüelemente** zum Öffnen der **Elemente-Editor** Dialogfeld.

   1. Klicken Sie auf **hinzufügen** dreimal drei Schaltflächen hinzufügen.

   1. Klicken Sie auf die erste Schaltfläche aus, und ändern Sie dann **Beschriftung** zu `New Window`, und **ID** zu `ID_WINDOW_NEW`.

   1. Klicken Sie auf die zweite Schaltfläche, und ändern Sie dann **Beschriftung** zu `Cascade`, und **ID** zu `ID_WINDOW_CASCADE`.

   1. Klicken Sie auf die dritte Schaltfläche, und ändern Sie dann **Beschriftung** zu `Tile`, und **ID** zu `ID_WINDOW_TILE_HORZ`.

1. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Die **Ansicht** und **Fenster** Bereiche angezeigt werden soll. Klicken Sie auf die Schaltfläche, um sicherzustellen, dass sie ordnungsgemäß funktionieren.

##  <a name="addhelppanel"></a> Hinzufügen eines Panels Hilfe zum Menüband

Sie können nun zwei Menüelemente, die in der Scribble-Anwendung auf die Schaltflächen auf dem Menüband definiert sind, mit dem Namen zuweisen **Hilfethemen** und **zu Scribble**. Die Schaltflächen werden hinzugefügt, um ein neuer Bereich mit dem Namen **Hilfe**.

### <a name="to-add-a-help-panel"></a>Zum Hinzufügen eines Bereichs der Hilfe

1. Von der **Toolbox**, ziehen Sie eine **Bereich** auf die **Startseite** Kategorie. Ziehen Sie zwei **Schaltflächen** den Zugriffsbereich.

1. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** zu `Help`.

1. Klicken Sie auf die erste Schaltfläche. Änderung **Beschriftung** zu `Help Topics`, und **ID** zu `ID_HELP_FINDER`.

1. Klicken Sie auf die zweite Schaltfläche. Änderung **Beschriftung** zu `About Scribble...`, und **ID** zu `ID_APP_ABOUT`.

1. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Ein **Hilfe** Bereich, der enthält zwei Schaltflächen auf dem Menüband angezeigt werden soll.

   > [!IMPORTANT]
   > Beim Klicken auf die **Hilfethemen** Schaltfläche die Scribble-Anwendung öffnet eine komprimierte HTML (chm)-Hilfedatei, die mit dem Namen *Your_project_name*. chm. Wenn Ihr Projekt nicht Scribble benannt ist, müssen Sie daher die Datei auf den Projektnamen umbenennen.

##  <a name="addpenpanel"></a> Hinzufügen eines Stift-Panels zum Menüband

Fügen Sie nun ein Panel angezeigt werden sollen, die die Stärke und die Farbe des Stifts steuern. Dieser Bereich enthält ein Kontrollkästchen, die zwischen thick und thin Stifte umschaltet. Die Funktionalität ähnelt der **dicker** Menüelements in der Scribble-Anwendung.

Die ursprüngliche Scribble-Anwendung ermöglicht dem Benutzer, die Breite des Stifts in einem Dialogfeld auswählen, die angezeigt wird, wenn der Benutzer klickt **Stift breiten** im Menü. Da die menübandleiste ausreichend Platz für neue Steuerelemente enthält, können Sie das Dialogfeld mit zwei Kombinationsfelder auf dem Menüband ersetzen. Ein Kombinationsfeld passt die Breite des Stifts schlanke und andere Kombinationsfeld passt die Breite des Stifts thick an.

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>Ein Stift-Felder für Bereich und Kombinationsfeld im Menüband hinzu

1. Von der **Toolbox**, ziehen Sie eine **Bereich** auf die **Startseite** Kategorie. Ziehen Sie dann eine **Kontrollkästchen** und zwei **Kombinationsfelder** den Zugriffsbereich.

1. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** zu `Pen`.

1. Klicken Sie auf das Kontrollkästchen. Änderung **Beschriftung** zu `Use Thick`, und **ID** zu `ID_PEN_THICK_OR_THIN`.

1. Klicken Sie auf der ersten Kombinationsfeld. Änderung **Beschriftung** zu `Thin Pen`, **ID** zu `ID_PEN_THIN_WIDTH`, **Typ** zu `Drop List`, **Daten** zu `1;2;3;4;5;6;7;8;9;`, und **Text** zu `2`.

1. Klicken Sie auf das zweite Kombinationsfeld. Änderung **Beschriftung** zu `Thick Pen`, **ID** zu `ID_PEN_THICK_WIDTH`, **Typ** zu `Drop List`, **Daten** zu `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`, und **Text** zu `5`.

1. Die neue Kombinationsfelder entsprechen keine vorhandenen Menüelemente, daher müssen Sie ein Menüelement für jede Stiftoption erstellen.

   1. In der **Ressourcenansicht** geöffnete Fenster die **IDR_SCRIBBTYPE** Menüressource.

   1. Klicken Sie auf **Stift** auf das Pen-Menü zu öffnen. Klicken Sie dann auf **Text hier eingeben** und `Thi&n Pen`.

   1. Mit der rechten Maustaste in des Texts, die von Ihnen zum Öffnen eingegebene der **Eigenschaften** Fenster, und klicken Sie dann ändern Sie die ID-Eigenschaft, um `ID_PEN_THIN_WIDTH`.

   1. Erstellen Sie einen Ereignishandler für jedes Menüelement Stift. Mit der rechten Maustaste die **Di & n Stift** Menüelement, das Sie erstellt, und klicken Sie dann auf **Ereignishandler hinzufügen**. Die **Ereignishandler-Assistent** wird angezeigt.

   1. In der **Klassenliste** wählen Sie im Assistenten im Feld **CScribbleDoc** , und klicken Sie dann auf **hinzufügen und Bearbeiten von**. Der Befehl erstellt einen Ereignishandler namens `CScribbleDoc::OnPenThinWidth`.

   1. Fügen Sie `CScribbleDoc::OnPenThinWidth` den folgenden Code hinzu.

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        // Get a pointer to the Thin Width combo box
        CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
        CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THIN_WIDTH));

        //Get the selected value
        int nCurSel = pThinComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThinWidth = atoi(CStringA(pThinComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. Als Nächstes erstellen Sie ein Menüelement Element und die Ereignishandler für die starke Stift.

   1. In der **Ressourcenansicht** geöffnete Fenster die **IDR_SCRIBBTYPE** Menüressource.

   1. Klicken Sie auf **Stift** auf das Pen-Menü zu öffnen. Klicken Sie dann auf **Text hier eingeben** und `Thic&k Pen`.

   1. Mit der rechten Maustaste in des Texts, die von Ihnen zum Anzeigen eingegebene der **Eigenschaften** Fenster. Ändern Sie die ID-Eigenschaft in `ID_PEN_THICK_WIDTH`.

   1. Mit der rechten Maustaste die **Stift dick** Menüelement, das Sie erstellt, und klicken Sie dann auf **Ereignishandler hinzufügen**. Die **Ereignishandler-Assistent** wird angezeigt.

   1. In der **Klassenliste** im Feld Wählen Sie im Assistenten **CScribbleDoc** , und klicken Sie dann auf **hinzufügen und Bearbeiten von**. Der Befehl erstellt einen Ereignishandler namens `CScribbleDoc::OnPenThickWidth`.

   1. Fügen Sie `CScribbleDoc::OnPenThickWidth` den folgenden Code hinzu.

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
            CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
        // Get the selected value
        int nCurSel = pThickComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThickWidth = atoi(CStringA(pThickComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Neue Schaltflächen und Kombinationsfelder angezeigt werden soll. Versuchen Sie es mit anderen Stift breiten scribble.

##  <a name="addcolorbutton"></a> Hinzufügen einer Schaltfläche "Farbe" auf den Stift-Bereich

Fügen Sie als Nächstes eine [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) -Objekt, das dem Benutzer ermöglicht Scribble in Farbe.

### <a name="to-add-a-color-button-to-the-pen-panel"></a>Eine Schaltfläche "Farbe" das Bedienfeld "Stift" hinzu

1. Bevor Sie die Schaltfläche "Farbe" hinzufügen, erstellen Sie ein Menüelement für. In der **Ressourcenansicht** geöffnete Fenster die **IDR_SCRIBBTYPE** Menüressource. Klicken Sie auf die **Stift** Menüelement, das Pen-Menü zu öffnen. Klicken Sie dann auf **Text hier eingeben** und `&Color`. Mit der rechten Maustaste in des Texts, die von Ihnen zum Anzeigen eingegebene der **Eigenschaften** Fenster. Ändern Sie die ID in `ID_PEN_COLOR`.

1. Fügen Sie jetzt die Schaltfläche "Farbe" hinzu. Von der **Toolbox**, ziehen Sie eine **Farbenschaltfläche** auf die **Stift** Bereich.

1. Klicken Sie auf die Schaltfläche "Farbe". Änderung **Beschriftung** zu `Color`, **ID** zu `ID_PEN_COLOR`, **Simple Look** zu `True`, **Large Image Index** auf `1`, und **Teilen Modus** zu `False`.

1. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Schaltfläche für die neue Farbe angezeigt werden soll, auf die **Stift** Bereich. Allerdings kann nicht verwendet werden, da er noch nicht über einen Ereignishandler verfügen. Die nächsten Schritte zeigen, wie einen Ereignishandler für die Schaltfläche "Farbe" hinzuzufügen.

##  <a name="addcolormember"></a> Hinzufügen eines Color-Members zur Dokumentklasse

Da die ursprüngliche Scribble-Anwendung Farbe Stifte hat, müssen Sie eine Implementierung für sie schreiben. Speichern die Stiftfarbe des Dokuments, die Dokumentenklasse, ein neues Mitglied hinzugefügt `CscribbleDoc`.

### <a name="to-add-a-color-member-to-the-document-class"></a>Der Dokumentklasse eine Color-Member hinzu

1. In scribdoc.h in der `CScribbleDoc` -Klasse der `// Attributes` Abschnitt. Fügen Sie die folgenden Codezeilen hinzu, nach der Definition von der `m_nThickWidth` -Datenmember.

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

1. Jedes Dokument enthält eine Liste der Tastenanschläge aufzeichnen, dass der Benutzer bereits gezeichnet hat. Jedes Strichs wird definiert, indem eine `CStroke` Objekt. Die `CStroke` Klasse keine Informationen zu Stiftfarbe, sodass Sie die Klasse ändern müssen. In scribdoc.h in der `CStroke` -Klasse verwenden, fügen Sie die folgenden Codezeilen, nach der Definition von der `m_nPenWidth` -Datenmember.

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

1. In scribdoc.h, fügen Sie einen neuen `CStroke` Konstruktor, dessen Parameter, Breite und Farbe angeben. Fügen Sie die folgende Zeile des Codes nach der `CStroke(UINT nPenWidth);` Anweisung.

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

1. Fügen Sie in scribdoc.cpp, die Implementierung der neuen `CStroke` Konstruktor. Fügen Sie den folgenden Code nach der Implementierung der `CStroke::CStroke(UINT nPenWidth)` Konstruktor.

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

1. Ändern Sie die zweite Zeile der `CStroke::DrawStroke` -Methode wie folgt.

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

1. Legen Sie die Standard-Stiftfarbe für die Dokumentklasse. In scribdoc.cpp, fügen Sie die folgenden Zeilen hinzu `CScribbleDoc::InitDocument`, nachdem die `m_nThickWidth = 5;` Anweisung.

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

1. In scribdoc.cpp, ändern Sie die erste Zeile der `CScribbleDoc::NewStroke` Methode, um die folgenden.

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

1. Ändern Sie die letzte Zeile der `CScribbleDoc::ReplacePen` Methode, um die folgenden.

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

1. Sie hinzugefügt haben die `m_penColor` Member in einem vorherigen Schritt. Nun erstellen Sie einen Ereignishandler für die Schaltfläche "Farbe", die das Element festlegt.

   1. In der **Ressourcenansicht** Fenster der Menüressource idr_scribbtype zu öffnen.

   1. Mit der rechten Maustaste die **Farbe** Menüelement, und klicken Sie auf **Ereignishandler hinzufügen**. Die **Ereignishandler-Assistent** angezeigt wird.

   1. In der **Klassenliste** wählen Sie im Assistenten im Feld **CScribbleDoc** , und klicken Sie dann auf die **hinzufügen und Bearbeiten von** Schaltfläche. Der Befehl erstellt die `CScribbleDoc::OnPenColor` Ereignisstubs-Handler.

1. Ersetzen Sie den Stub für die `CScribbleDoc::OnPenColor` -Ereignishandler durch den folgenden Code.

   ```cpp
   void CScribbleDoc::OnPenColor()
   {
       // Change pen color to reflect color button's current selection
       CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
       ASSERT_VALID(pRibbon);

       CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
           CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

       m_penColor = pColorBtn->GetColor();
       // Create new pen using the selected color
       ReplacePen();
   }
   ```

1. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Sie können jetzt drücken Sie die Schaltfläche "Farbe" und ändern die Stiftfarbe.

##  <a name="initpensave"></a> Initialisieren die Stifte, und Speichern von Einstellungen

Als Nächstes initialisieren Sie die Farbe und Breite der Stifte. Zum Schluss speichern Sie und Laden Sie eine Farbe aus einer Datei.

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>Zum Initialisieren der Steuerelemente auf der menübandleiste

1. Initialisieren Sie die Stifte in der menübandleiste.

   Fügen Sie den folgenden Code zum scribdoc.cpp, in der `CScribbleDoc::InitDocument` Methode nach der `m_sizeDoc = CSize(200,200)` Anweisung.

   ```cpp
   // Reset the ribbon UI to its initial values
   CMFCRibbonBar* pRibbon =
       ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
   ASSERT_VALID(pRibbon);

   CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
       CMFCRibbonColorButton,
       pRibbon->FindByID(ID_PEN_COLOR));

   // Set ColorButton to black
   pColorBtn->SetColor(RGB(0, 0, 0));

   CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THIN_WIDTH));

   // Set Thin pen combobox to 2
   pThinComboBox->SelectItem(1);

   CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THICK_WIDTH));

   // Set Thick pen combobox to 5
   pThickComboBox->SelectItem(0);
   ```

1. Speichern Sie eine Farbe in eine Datei zu zeichnen. Fügen Sie die folgende Anweisung zum scribdoc.cpp, in der `CStroke::Serialize` Methode nach der `ar << (WORD)m_nPenWidth;` Anweisung.

   ```cpp
   ar << (COLORREF)m_penColor;
   ```

1. Laden Sie dann eine Farbe aus einer Datei. Fügen Sie die folgende Zeile des Codes, in der `CStroke::Serialize` Methode nach der `m_nPenWidth = w;` Anweisung.

   ```cpp
   ar >> m_penColor;
   ```

1. Jetzt scribble in Farbe und die Zeichnung in einer Datei speichern.

## <a name="conclusion"></a>Schlussbemerkung

Sie haben die MFC Scribble-Anwendung aktualisiert. Verwenden Sie in dieser exemplarischen Vorgehensweise als Leitfaden, wenn Sie Ihre vorhandenen Anwendungen ändern.

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)<br/>
[Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)
