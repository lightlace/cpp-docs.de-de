---
title: 'Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 2) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 351aea09376d6cba7f091828225fd337fa3f68e1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423160"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 2)

[Teil 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) dieser exemplarischen Vorgehensweise wurde gezeigt, wie Sie ein Office Fluent-Multifunktionsleiste klassischen hinzufügen Scribble-Anwendung. Dieser Teil zeigt das Hinzufügen von menübandbereichen und Steuerelementen, die Benutzer anstelle von Menüs und Befehlen verwenden können.

## <a name="prerequisites"></a>Erforderliche Komponenten

[Visual C++-Beispiele](../visual-cpp-samples.md)

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

   2. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** zu `View`.

   3. Klicken Sie auf das erste Kontrollkästchen, um seine Eigenschaften zu ändern. Änderung **ID** zu `ID_VIEW_TOOLBAR` und **Beschriftung** zu `Toolbar`.

   4. Klicken Sie auf das zweite Kontrollkästchen, um seine Eigenschaften zu ändern. Änderung **ID** zu `ID_VIEW_STATUS_BAR` und **Beschriftung** zu `Status Bar`.

2. Erstellen Sie einen Bereich mit dem Namen `Window` , die eine unterteilte Schaltfläche verfügt. Wenn ein Benutzer die unterteilte Schaltfläche klickt, zeigt ein Kontextmenü drei Befehle, die bereits in der Scribble-Anwendung definiert sind.

   1. Von der **Toolbox**, ziehen Sie eine **Bereich** auf die **Startseite** Kategorie. Ziehen Sie dann eine **Schaltfläche** den Zugriffsbereich.

   2. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** zu `Window`.

   3. Klicken Sie auf die Schaltfläche. Änderung **Beschriftung** zu `Windows`, **Schlüssel** zu `w`, **Large Image Index** zu `1`, und **Teilen Modus** um `False`. Klicken Sie dann auf die Auslassungspunkte (**...** ) neben **Menüelemente** zum Öffnen der **Elemente-Editor** Dialogfeld.

   4. Klicken Sie auf **hinzufügen** dreimal drei Schaltflächen hinzufügen.

   5. Klicken Sie auf die erste Schaltfläche aus, und ändern Sie dann **Beschriftung** zu `New Window`, und **ID** zu `ID_WINDOW_NEW`.

   6. Klicken Sie auf die zweite Schaltfläche, und ändern Sie dann **Beschriftung** zu `Cascade`, und **ID** zu `ID_WINDOW_CASCADE`.

   7. Klicken Sie auf die dritte Schaltfläche, und ändern Sie dann **Beschriftung** zu `Tile`, und **ID** zu `ID_WINDOW_TILE_HORZ`.

3. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Die **Ansicht** und **Fenster** Bereiche angezeigt werden soll. Klicken Sie auf die Schaltfläche, um sicherzustellen, dass sie ordnungsgemäß funktionieren.

[[Abschnitte](#top)]

##  <a name="addhelppanel"></a> Hinzufügen eines Panels Hilfe zum Menüband

Sie können nun zwei Menüelemente, die in der Scribble-Anwendung auf die Schaltflächen auf dem Menüband definiert sind, mit dem Namen zuweisen **Hilfethemen** und **zu Scribble**. Die Schaltflächen werden hinzugefügt, um ein neuer Bereich mit dem Namen **Hilfe**.

### <a name="to-add-a-help-panel"></a>Zum Hinzufügen eines Bereichs der Hilfe

1. Von der **Toolbox**, ziehen Sie eine **Bereich** auf die **Startseite** Kategorie. Ziehen Sie zwei **Schaltflächen** den Zugriffsbereich.

2. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** zu `Help`.

3. Klicken Sie auf die erste Schaltfläche. Änderung **Beschriftung** zu `Help Topics`, und **ID** zu `ID_HELP_FINDER`.

4. Klicken Sie auf die zweite Schaltfläche. Änderung **Beschriftung** zu `About Scribble...`, und **ID** zu `ID_APP_ABOUT`.

5. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Ein **Hilfe** Bereich, der enthält zwei Schaltflächen auf dem Menüband angezeigt werden soll.

   > [!IMPORTANT]
   > Beim Klicken auf die **Hilfethemen** Schaltfläche die Scribble-Anwendung öffnet eine komprimierte HTML (chm)-Hilfedatei, die mit dem Namen *Your_project_name*. chm. Wenn Ihr Projekt nicht Scribble benannt ist, müssen Sie daher die Datei auf den Projektnamen umbenennen.

[[Abschnitte](#top)]

##  <a name="addpenpanel"></a> Hinzufügen eines Stift-Panels zum Menüband

Fügen Sie nun ein Panel angezeigt werden sollen, die die Stärke und die Farbe des Stifts steuern. Dieser Bereich enthält ein Kontrollkästchen, die zwischen thick und thin Stifte umschaltet. Die Funktionalität ähnelt der **dicker** Menüelements in der Scribble-Anwendung.

Die ursprüngliche Scribble-Anwendung ermöglicht dem Benutzer, die Breite des Stifts in einem Dialogfeld auswählen, die angezeigt wird, wenn der Benutzer klickt **Stift breiten** im Menü. Da die menübandleiste ausreichend Platz für neue Steuerelemente enthält, können Sie das Dialogfeld mit zwei Kombinationsfelder auf dem Menüband ersetzen. Ein Kombinationsfeld passt die Breite des Stifts schlanke und andere Kombinationsfeld passt die Breite des Stifts thick an.

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>Ein Stift-Felder für Bereich und Kombinationsfeld im Menüband hinzu

1. Von der **Toolbox**, ziehen Sie eine **Bereich** auf die **Startseite** Kategorie. Ziehen Sie dann eine **Kontrollkästchen** und zwei **Kombinationsfelder** den Zugriffsbereich.

2. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** zu `Pen`.

3. Klicken Sie auf das Kontrollkästchen. Änderung **Beschriftung** zu `Use Thick`, und **ID** zu `ID_PEN_THICK_OR_THIN`.

4. Klicken Sie auf der ersten Kombinationsfeld. Änderung **Beschriftung** zu `Thin Pen`, **ID** zu `ID_PEN_THIN_WIDTH`, **Text** zu `2`, **Typ** zu `Drop List`, und **Daten** zu `1;2;3;4;5;6;7;8;9;`.

5. Klicken Sie auf das zweite Kombinationsfeld. Änderung **Beschriftung** zu `Thick Pen`, **ID** zu `ID_PEN_THICK_WIDTH`, **Text** zu `5`, **Typ** zu `Drop List`, und **Daten** zu `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`.

6. Die neue Kombinationsfelder entsprechen keine vorhandenen Menüelementen. Aus diesem Grund müssen Sie ein Menüelement für jede Stiftoption erstellen.

   1. In der **Ressourcenansicht** Fenster der Menüressource idr_scribbtype zu öffnen.

   2. Klicken Sie auf **Stift** , öffnen Sie das p**En** Menü. Klicken Sie dann auf **Text hier eingeben** und `Thi&n Pen`.

   3. Mit der rechten Maustaste in des Texts, der Sie gerade eingegeben, zum Öffnen haben der **Eigenschaften** Fenster, und klicken Sie dann ändern Sie die ID-Eigenschaft, um `ID_PEN_THIN_WIDTH`.

   4. Sie müssen auch einen Ereignishandler für jedes Menüelement Stift erstellen. Mit der rechten Maustaste die **Di & n Stift** Menüelement, das Sie gerade erstellt haben, und klicken Sie dann auf **Ereignishandler hinzufügen**. Die **Ereignishandler-Assistent** wird angezeigt.

   5. In der **Klassenliste** wählen Sie im Assistenten im Feld **CScribbleDoc** , und klicken Sie dann auf **hinzufügen und Bearbeiten von**. Dadurch wird einen Ereignishandler mit dem Namen erstellt `CScribbleDoc::OnPenThinWidth`.

   6. Fügen Sie `CScribbleDoc::OnPenThinWidth` den folgenden Code hinzu.

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
        m_nThinWidth = atoi(pThinComboBox->GetItem(nCurSel));
    }

    // Create a new pen using the selected width
    ReplacePen();
    ```

7. Als Nächstes erstellen Sie ein Menüelement Element und die Ereignishandler für die starke Stift.

   1. In der **Ressourcenansicht** Fenster der Menüressource idr_scribbtype zu öffnen.

   2. Klicken Sie auf **Stift** auf das Pen-Menü zu öffnen. Klicken Sie dann auf **Text hier eingeben** und `Thic&k Pen`.

   3. Mit der rechten Maustaste in des Texts, der Sie gerade eingegeben, zum Anzeigen haben der **Eigenschaften** Fenster. Ändern Sie die ID-Eigenschaft in `ID_PEN_THICK_WIDTH`.

   4. Mit der rechten Maustaste die **Stift dick** Menüelement, das Sie gerade erstellt haben, und klicken Sie dann auf **Ereignishandler hinzufügen**. Die **Ereignishandler-Assistent** wird angezeigt.

   5. In der **Klassenliste** im Feld Wählen Sie im Assistenten **CScribbleDoc** , und klicken Sie dann auf **hinzufügen und Bearbeiten von**. Dadurch wird einen Ereignishandler mit dem Namen erstellt `CScribbleDoc::OnPenThickWidth`.

   6. Fügen Sie `CScribbleDoc::OnPenThickWidth` den folgenden Code hinzu.

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
          m_nThickWidth = atoi(pThickComboBox->GetItem(nCurSel));
      }

      // Create a new pen using the selected width
      ReplacePen();
      ```

8. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Neue Schaltflächen und Kombinationsfelder angezeigt werden soll. Versuchen Sie es mit anderen Stift breiten scribble.

[[Abschnitte](#top)]

##  <a name="addcolorbutton"></a> Hinzufügen einer Schaltfläche "Farbe" auf den Stift-Bereich

Fügen Sie als Nächstes eine [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) -Objekt, das dem Benutzer ermöglicht Scribble in Farbe.

### <a name="to-add-a-color-button-to-the-pen-panel"></a>Eine Schaltfläche "Farbe" das Bedienfeld "Stift" hinzu

1. Bevor Sie die Schaltfläche "Farbe" hinzufügen, erstellen Sie ein Menüelement für. In der **Ressourcenansicht** Fenster der Menüressource idr_scribbtype zu öffnen. Klicken Sie auf die **Stift** Menüelement, das Pen-Menü zu öffnen. Klicken Sie dann auf **Text hier eingeben** und `&Color`. Mit der rechten Maustaste in des Texts, der Sie gerade eingegeben, zum Anzeigen haben der **Eigenschaften** Fenster. Ändern Sie die ID, `ID_PEN_COLOR`.

2. Fügen Sie jetzt die Schaltfläche "Farbe" hinzu. Von der **Toolbox**, ziehen Sie eine **Farbenschaltfläche** auf die **Stift** Bereich.

3. Klicken Sie auf die Schaltfläche "Farbe". Änderung **Beschriftung** zu `Color`, **ID** zu `ID_PEN_COLOR`, **SimpleLook** zu `True`, **Large Image Index** auf `1`, und **Teilen Modus** zu `False`.

4. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Schaltfläche für die neue Farbe angezeigt werden soll, auf die **Stift** Bereich. Allerdings kann nicht verwendet werden, da er noch nicht über einen Ereignishandler verfügt. Die nächsten Schritte zeigen, wie einen Ereignishandler für die Schaltfläche "Farbe" hinzuzufügen.

[[Abschnitte](#top)]

##  <a name="addcolormember"></a> Hinzufügen eines Color-Members zur Dokumentklasse

Da die ursprüngliche Scribble-Anwendung keine Farbe Stifte, müssen Sie eine Implementierung für sie schreiben. Um die Stiftfarbe des Dokuments zu speichern, fügen Sie ein neues Mitglied der Dokument-Klasse, `CscribbleDoc.`

### <a name="to-add-a-color-member-to-the-document-class"></a>Der Dokumentklasse eine Color-Member hinzu

1. In scribdoc.h in der `CScribbleDoc` -Klasse der `// Attributes` Abschnitt. Fügen Sie die folgenden Codezeilen hinzu, nach der Definition von der `m_nThickWidth` -Datenmember.

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

2. Jedes Dokument enthält eine Liste der Tastenanschläge aufzeichnen, dass der Benutzer bereits gezeichnet hat. Jedes Strichs wird definiert, indem eine `CStroke` Objekt. Die `CStroke` Klasse enthält keine Informationen über die Stiftfarbe. Aus diesem Grund müssen Sie die Klasse ändern. In scribdoc.h in der `CStroke` -Klasse verwenden, fügen Sie die folgenden Codezeilen, nach der Definition von der `m_nPenWidth` -Datenmember.

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

3. In scribdoc.h, fügen Sie einen neuen `CStroke` Konstruktor, dessen Parameter, Breite und Farbe angeben. Fügen Sie die folgende Zeile des Codes nach der `CStroke(UINT nPenWidth);` Anweisung.

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

4. Fügen Sie in scribdoc.cpp, die Implementierung der neuen `CStroke` Konstruktor. Fügen Sie den folgenden Code nach der Implementierung der `CStroke::CStroke(UINT nPenWidth)` Konstruktor.

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

5. Ändern Sie die zweite Zeile der `CStroke::DrawStroke` -Methode wie folgt.

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

6. Legen Sie die Standard-Stiftfarbe für die Dokumentklasse. In scribdoc.cpp, fügen Sie die folgenden Zeilen hinzu `CScribbleDoc::InitDocument`, nachdem die `m_nThickWidth = 5;` Anweisung.

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

7. In scribdoc.cpp, ändern Sie die erste Zeile der `CScribbleDoc::NewStroke` Methode, um die folgenden.

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

8. Ändern Sie die letzte Zeile der `CScribbleDoc::ReplacePen` Methode, um die folgenden.

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

9. Sie hinzugefügt haben die `m_penColor` Member in einem vorherigen Schritt. Nun erstellen Sie einen Ereignishandler für die Schaltfläche "Farbe", die das Element festlegt.

   1. In der **Ressourcenansicht** Fenster der Menüressource idr_scribbtype zu öffnen.

   2. Mit der rechten Maustaste die **Farbe** Menüelement, und klicken Sie auf **Ereignishandler hinzufügen**. Die **Ereignishandler-Assistent** angezeigt wird.

   3. In der **Klassenliste** wählen Sie im Assistenten im Feld **CScribbleDoc** , und klicken Sie dann auf die **hinzufügen und Bearbeiten von** Schaltfläche. Dies erstellt die `CScribbleDoc::OnPenColor` Ereignisstubs-Handler.

10. Ersetzen Sie den Stub für die `CScribbleDoc::OnPenColor` -Ereignishandler durch den folgenden Code.

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

11. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Sie sollten in der Lage, drücken die Schaltfläche "Farbe", und ändern Sie die Stiftfarbe.

[[Abschnitte](#top)]

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

2. Speichern Sie eine Farbe in eine Datei zu zeichnen. Fügen Sie die folgende Anweisung zum scribdoc.cpp, in der `CStroke::Serialize` Methode nach der `ar << (WORD)m_nPenWidth;` Anweisung.

   ```cpp
   ar << (COLORREF)m_penColor;
    ```

3. Laden Sie dann eine Farbe aus einer Datei. Fügen Sie die folgende Zeile des Codes, in der `CStroke::Serialize` Methode nach der `m_nPenWidth = w;` Anweisung.

   ```cpp
   ar >> m_penColor;
   ```

4. Jetzt scribble in Farbe und die Zeichnung in einer Datei speichern.

[[Abschnitte](#top)]

## <a name="conclusion"></a>Schlussbemerkung

Sie haben die MFC Scribble-Anwendung aktualisiert. Verwenden Sie in dieser exemplarischen Vorgehensweise als Leitfaden, wenn Sie Ihre vorhandenen Anwendungen ändern.

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)<br/>
[Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)
