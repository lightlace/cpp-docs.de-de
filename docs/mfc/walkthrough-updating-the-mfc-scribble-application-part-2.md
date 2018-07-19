---
title: 'Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 2) | Microsoft Docs'
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
ms.openlocfilehash: bccc10e1aa2d984486c3cadfd45a14a6625ec959
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122403"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 2)

[Teil 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) Scribble-Anwendung in dieser exemplarischen Vorgehensweise wurde gezeigt, wie das klassische Office Fluent-Menüband hinzugefügt. In diesem Teil werden zum Hinzufügen von menübandbereichen und Steuerelemente, die Benutzer anstelle von Menüs und Befehle verwenden können.

## <a name="prerequisites"></a>Erforderliche Komponenten

[Visual C++-Beispiele](../visual-cpp-samples.md)

##  <a name="top"></a> Abschnitte

Dieser Teil der exemplarischen Vorgehensweise enthält die folgenden Abschnitte:

- [Hinzufügen neuer Bereiche zum Menüband](#addnewpanel)

- [Hinzufügen einer Hilfebereich zum Menüband](#addhelppanel)

- [Hinzufügen einen Stift Bereich zum Menüband](#addpenpanel)

- [Hinzufügen einer Schaltfläche "Farbe" zum Menüband](#addcolorbutton)

- [Hinzufügen eines Color-Members der Dokument-Klasse](#addcolormember)

- [Initialisieren die Stifte, und speichern die Voreinstellungen](#initpensave)

##  <a name="addnewpanel"></a> Hinzufügen neuer Bereiche zum Menüband

Diese Schritte zeigen, wie hinzufügen eine **Ansicht** Bereich, der zwei Kontrollkästchen enthält, die die Sichtbarkeit der Symbolleiste und die Statusleiste steuern sowie eine **Fenster** Bereich, der eine vertikal ausgerichtet Teilung enthält Schaltfläche ", die die Erstellung und die Anordnung von Multiple Document Interface (MDI) Windows steuert.

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>Die menübandleiste Sichtbereich und Fenster-Bereich hinzufügen

1. Erstellen Sie einen Bereich mit dem Namen `View`, verfügt über zwei Kontrollkästchen angezeigt, die die Symbolleiste und Statusleiste umzuschalten.

   1. Aus der **Toolbox**, ziehen Sie eine **Bereich** auf die **Home** Kategorie. Ziehen Sie zwei **Kontrollkästchen** in den Bereich.

   2. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** auf `View`.

   3. Klicken Sie auf das erste Kontrollkästchen, um seine Eigenschaften zu ändern. Änderung **ID** auf `ID_VIEW_TOOLBAR` und **Beschriftung** auf `Toolbar`.

   4. Klicken Sie auf das zweite Kontrollkästchen, um seine Eigenschaften zu ändern. Änderung **ID** auf `ID_VIEW_STATUS_BAR` und **Beschriftung** auf `Status Bar`.

2. Erstellen Sie einen Bereich mit dem Namen `Window` , die eine unterteilte Schaltfläche verfügt. Wenn ein Benutzer die unterteilte Schaltfläche klickt, zeigt ein Kontextmenü drei Befehle, die bereits in der Scribble-Anwendung definiert sind.

   1. Aus der **Toolbox**, ziehen Sie eine **Bereich** auf die **Home** Kategorie. Ziehen Sie dann eine **Schaltfläche** in den Bereich.

   2. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** auf `Window`.

   3. Klicken Sie auf die Schaltfläche. Änderung **Beschriftung** auf `Windows`, **Schlüssel** auf `w`, **große Abbildindex** auf `1`, und **Teilen Modus** um `False`. Klicken Sie dann auf die Auslassungspunkte (**...** ) neben **Menüelemente** So öffnen die **Elemente-Editor** (Dialogfeld).

   4. Klicken Sie auf **hinzufügen** dreimal drei Schaltflächen hinzufügen.

   5. Klicken Sie auf die erste Schaltfläche aus, und ändern Sie dann **Beschriftung** auf `New Window`, und **ID** auf `ID_WINDOW_NEW`.

   6. Klicken Sie auf die zweite Schaltfläche aus, und ändern Sie dann **Beschriftung** auf `Cascade`, und **ID** auf `ID_WINDOW_CASCADE`.

   7. Klicken Sie auf die dritte Schaltfläche aus, und ändern Sie dann **Beschriftung** auf `Tile`, und **ID** auf `ID_WINDOW_TILE_HORZ`.

3. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Die **Ansicht** und **Fenster** Bereiche angezeigt werden soll. Klicken Sie auf die Schaltflächen, um sicherzustellen, dass sie ordnungsgemäß funktionieren.

[[Abschnitte](#top)]

##  <a name="addhelppanel"></a> Hinzufügen einer Hilfebereich zum Menüband

Sie können nun zwei Menüelemente, die in der Scribble-Anwendung zu Menübandschaltflächen definiert sind, die mit dem Namen sind zuweisen **Hilfethemen** und **zu Scribble**. Die Schaltflächen werden hinzugefügt, um einen neuen Bereich namens **Hilfe**.

### <a name="to-add-a-help-panel"></a>So fügen Sie ein Panel Hilfe hinzu

1. Aus der **Toolbox**, ziehen Sie eine **Bereich** auf die **Home** Kategorie. Ziehen Sie zwei **Schaltflächen** in den Bereich.

2. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** auf `Help`.

3. Klicken Sie auf die erste Schaltfläche. Änderung **Beschriftung** auf `Help Topics`, und **ID** auf `ID_HELP_FINDER`.

4. Klicken Sie auf die zweite Schaltfläche. Änderung **Beschriftung** auf `About Scribble...`, und **ID** auf `ID_APP_ABOUT`.

5. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Ein **Hilfe** Bereich, der zwei Menübandschaltflächen enthält angezeigt werden soll.

   > [!IMPORTANT]
   > Beim Klicken auf die **Hilfethemen** Schaltfläche Scribble-Anwendung öffnet eine komprimierte HTML (chm)-Hilfedatei, die mit dem Namen *Your_project_name*. chm. Wenn das Projekt nicht Scribble benannt wird, müssen Sie daher die Hilfedatei auf den Projektnamen umbenennen.

[[Abschnitte](#top)]

##  <a name="addpenpanel"></a> Hinzufügen einen Stift Bereich zum Menüband

Fügen Sie nun ein Panel um Schaltflächen anzuzeigen, die die Stärke und die Farbe des Stifts steuern. Dieser Bereich enthält ein Kontrollkästchen, die zwischen thick und thin Stifte umschaltet. Die Funktionalität ähnelt dem von der **starke Linie** Menüelement in der Scribble-Anwendung.

Die ursprüngliche Scribble-Anwendung ermöglicht dem Benutzer, die Breite des Stifts in einem Dialogfeld auswählen, die angezeigt wird, wenn der Benutzer klickt auf **Stift breiten** auf das Menü. Da die menübandleiste ausreichend Platz für neue Steuerelemente enthält, können Sie das Dialogfeld mit zwei Kombinationsfelder auf dem Menüband ersetzen. Ein Kombinationsfeld passt die Breite des Stifts schlanke und andere Kombinationsfeld passt die Breite des Stifts thick.

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>Ein Stift Bereich und Kombinationsfelder Felder zum Menüband hinzufügen

1. Aus der **Toolbox**, ziehen Sie eine **Bereich** auf die **Home** Kategorie. Ziehen Sie dann eine **Kontrollkästchen** und zwei **Kombinationsfelder** in den Bereich.

2. Klicken Sie auf den Bereich, um seine Eigenschaften zu ändern. Änderung **Beschriftung** auf `Pen`.

3. Klicken Sie auf das Kontrollkästchen. Änderung **Beschriftung** auf `Use Thick`, und **ID** auf `ID_PEN_THICK_OR_THIN`.

4. Klicken Sie auf das erste Kombinationsfeld. Änderung **Beschriftung** auf `Thin Pen`, **ID** auf `ID_PEN_THIN_WIDTH`, **Text** auf `2`, **Typ** auf `Drop List`, und **Daten** auf `1;2;3;4;5;6;7;8;9;`.

5. Klicken Sie auf das zweite Kombinationsfeld. Änderung **Beschriftung** auf `Thick Pen`, **ID** auf `ID_PEN_THICK_WIDTH`, **Text** auf `5`, **Typ** auf `Drop List`, und **Daten** auf `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`.

6. Die neue Kombinationsfelder müssen keine vorhandenen Menüelementen entsprechen. Aus diesem Grund müssen Sie ein Menüelement für jede Stiftoption erstellen.

   1. In der **Ressourcenansicht** Fenster der Menüressource idr_scribbtype zu öffnen.

   2. Klicken Sie auf **Stift** , öffnen Sie die p**En** Menü. Klicken Sie dann auf **hier eingeben** und Typ `Thi&n Pen`.

   3. Mit der rechten Maustaste in des Texts, den Sie gerade eingegeben, zum Öffnen haben der **Eigenschaften** Fenster, und klicken Sie dann ändern Sie die ID-Eigenschaft, um `ID_PEN_THIN_WIDTH`.

   4. Sie müssen auch einen Ereignishandler für jedes Element der Stift im Menü erstellen. Mit der rechten Maustaste die **Di & n Stift** Menüelement, das Sie gerade erstellt haben, und klicken Sie dann auf **Ereignishandler hinzufügen**. Die **Ereignishandler-Assistent** wird angezeigt.

   5. In der **Klassenliste** Feld mit dem Assistenten die Option **CScribbleDoc** , und klicken Sie dann auf **hinzufügen und Bearbeiten von**. Dies erstellt einen Ereignishandler namens `CScribbleDoc::OnPenThinWidth`.

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

7. Als Nächstes erstellen Sie ein Menü Element und Ereignishandlern, für die starke Stift.

   1. In der **Ressourcenansicht** Fenster der Menüressource idr_scribbtype zu öffnen.

   2. Klicken Sie auf **Stift** Stiftmenü zu öffnen. Klicken Sie dann auf **hier eingeben** und Typ `Thic&k Pen`.

   3. Mit der rechten Maustaste in des Texts, die Sie gerade eingegeben, zum Anzeigen haben der **Eigenschaften** Fenster. Ändern Sie die ID-Eigenschaft in `ID_PEN_THICK_WIDTH`.

   4. Mit der rechten Maustaste die **Stift dick** Menüelement, das Sie gerade erstellt haben, und klicken Sie dann auf **Ereignishandler hinzufügen**. Die **Ereignishandler-Assistent** wird angezeigt.

   5. In der **Klassenliste** Feld Wählen Sie im Assistenten **CScribbleDoc** , und klicken Sie dann auf **hinzufügen und Bearbeiten von**. Dies erstellt einen Ereignishandler namens `CScribbleDoc::OnPenThickWidth`.

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

8. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Neue Schaltflächen und Kombinationsfelder sollte angezeigt werden. Versuchen Sie es mit anderen Stift breiten scribble.

[[Abschnitte](#top)]

##  <a name="addcolorbutton"></a> Eine Farbenschaltfläche hinzufügen, wenn des Stift-Bereichs

Als Nächstes fügen Sie eine [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) -Objekt, das dem Benutzer kann Scribble in Farbe.

### <a name="to-add-a-color-button-to-the-pen-panel"></a>So fügen Sie eine farbenschaltfläche, wenn der Stift Bereich hinzu

1. Bevor Sie auf die Farbschaltfläche hinzufügen, erstellen Sie ein Menüelement für. In der **Ressourcenansicht** Fenster der Menüressource idr_scribbtype zu öffnen. Klicken Sie auf die **Stift** Menüelement, um den Stiftmenü zu öffnen. Klicken Sie dann auf **hier eingeben** und Typ `&Color`. Mit der rechten Maustaste in des Texts, die Sie gerade eingegeben, zum Anzeigen haben der **Eigenschaften** Fenster. Ändern Sie die ID in `ID_PEN_COLOR`.

2. Nun fügen Sie die Schaltfläche "Farbe" hinzu. Aus der **Toolbox**, ziehen Sie eine **Farbenschaltfläche** auf die **Stift** Bereich.

3. Klicken Sie auf die Farbschaltfläche. Änderung **Beschriftung** auf `Color`, **ID** auf `ID_PEN_COLOR`, **SimpleLook** auf `True`, **große Abbildindex** auf `1`, und **Teilen Modus** auf `False`.

4. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Schaltfläche für die neue Farbe angezeigt werden soll, auf die **Stift** Bereich. Allerdings kann nicht verwendet werden, da er noch nicht über einen Ereignishandler verfügt. Die nächsten Schritte zeigen, wie ein Ereignishandler für die Schaltfläche "Farbe" hinzugefügt.

[[Abschnitte](#top)]

##  <a name="addcolormember"></a> Hinzufügen eines Color-Members der Dokument-Klasse

Da die ursprüngliche Scribble-Anwendung keine Farbe Stifte, müssen Sie eine Implementierung dafür schreiben. Um die Stiftfarbe des Dokuments zu speichern, fügen Sie ein neues Element der Dokument-Klasse, `CscribbleDoc.`

### <a name="to-add-a-color-member-to-the-document-class"></a>Die Dokumentklasse Color-Member hinzu

1. In scribdoc.h in der `CScribbleDoc` Klasse aus, suchen Sie die `// Attributes` Abschnitt. Fügen Sie die folgenden Codezeilen hinzu, nach der Definition von der `m_nThickWidth` -Datenmember.

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

2. Jedes Dokument enthält eine Liste der Striche, dass der Benutzer bereits gezeichnet wurde. Jeder Strich wird definiert, indem ein `CStroke` Objekt. Die `CStroke` Klasse enthält keine Informationen zu Stiftfarbe. Aus diesem Grund müssen Sie die Klasse ändern. In scribdoc.h in der `CStroke` -Klasse verwenden, fügen Sie die folgenden Codezeilen nach der Definition der `m_nPenWidth` -Datenmember.

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

3. In scribdoc.h, fügen Sie einen neuen `CStroke` Konstruktor, dessen Parameter Breite und Farbe angeben. Fügen Sie die folgende Zeile des Codes nach der `CStroke(UINT nPenWidth);` Anweisung.

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

4. In scribdoc.cpp, fügen Sie die Implementierung der neuen `CStroke` Konstruktor. Fügen Sie den folgenden Code nach der Implementierung der `CStroke::CStroke(UINT nPenWidth)` Konstruktor.

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

5. Ändern Sie die zweite Zeile der `CStroke::DrawStroke` Methode wie folgt.

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

6. Legen Sie die Standard-Stiftfarbe für die Document-Klasse. Fügen Sie die folgenden Zeilen, die in scribdoc.cpp, `CScribbleDoc::InitDocument`nach der `m_nThickWidth = 5;` Anweisung.

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

7. In scribdoc.cpp, ändern Sie die erste Zeile der `CScribbleDoc::NewStroke` Methode, um die folgenden.

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

8. Ändern die letzte Zeile der `CScribbleDoc::ReplacePen` Methode, um die folgenden.

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

9. Hinzugefügte der `m_penColor` Member in einem vorherigen Schritt. Nun erstellen Sie einen Ereignishandler für die Schaltfläche für die Farbe, die das Element festlegt.

   1. In der **Ressourcenansicht** Fenster der Menüressource idr_scribbtype zu öffnen.

   2. Mit der rechten Maustaste die **Farbe** Menüelement und klicken Sie auf **Ereignishandler hinzufügen**. Die **Ereignishandler-Assistent** angezeigt wird.

   3. In der **Klassenliste** Feld mit dem Assistenten die Option **CScribbleDoc** , und klicken Sie dann auf die **hinzufügen und Bearbeiten von** Schaltfläche. Dies erstellt die `CScribbleDoc::OnPenColor` Ereignishandlerstub.

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

11. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus. Sie sollten Lage, drücken die Farbe und den Stift Farbe ändern.

[[Abschnitte](#top)]

##  <a name="initpensave"></a> Initialisieren die Stifte, und speichern die Voreinstellungen

Als Nächstes initialisieren Sie die Farbe und Breite der Stifte. Schließlich speichern Sie und Laden Sie eine Farbe aus einer Datei zeichnen.

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>Steuerelemente auf der menübandleiste initialisiert werden.

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

2. Speichern Sie eine Farbe in eine Datei zeichnen. Fügen Sie die folgende Anweisung zum scribdoc.cpp, in der `CStroke::Serialize` Methode nach der `ar << (WORD)m_nPenWidth;` Anweisung.

   ```cpp
   ar << (COLORREF)m_penColor;
    ```

3. Laden Sie schließlich eine Farbe aus einer Datei zeichnen. Fügen Sie die folgende Codezeile der `CStroke::Serialize` Methode nach der `m_nPenWidth = w;` Anweisung.

   ```cpp
   ar >> m_penColor;
   ```

4. Jetzt scribble in Farbe und die Zeichnung in einer Datei speichern.

[[Abschnitte](#top)]

## <a name="conclusion"></a>Schlussbemerkung

Sie haben die MFC Scribble-Anwendung aktualisiert. Verwenden Sie in dieser exemplarischen Vorgehensweise als Leitfaden, wenn Sie vorhandenen Anwendungen ändern.

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)  
[Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)  
