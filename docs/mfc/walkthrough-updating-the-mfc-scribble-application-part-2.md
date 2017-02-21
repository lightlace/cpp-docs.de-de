---
title: "Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 2) | Microsoft Docs"
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
  - "Exemplarische Vorgehensweisen [C++]"
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 2)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Teil 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) dieser exemplarischen Vorgehensweise angezeigt, wie einen fließenden Menüband Office der klassischen Scribble\-Anwendung hinzufügt.  Dieser Teil wird gezeigt, wie Menübandbereiche und Steuerelemente hinzugefügt werden, dass Benutzer statt der Menüs und der Befehle verwenden können.  
  
## Vorbereitungsmaßnahmen  
 [Visual C\+\+\-Beispiele](../top/visual-cpp-samples.md)  
  
##  <a name="top"></a> Abschnitte  
 Dieser Teil der exemplarischen Vorgehensweise enthält die folgenden Abschnitte:  
  
-   [Hinzufügen von neuen Bereichen zum Menüband](#addNewPanel)  
  
-   [Hinzufügen eines Hilfe\-Bereichs zum Menüband](#addHelpPanel)  
  
-   [Hinzufügen eines Stifts\-Bereichs zum Menüband](#addPenPanel)  
  
-   [Hinzufügen einer Farben\-Schaltfläche zum Menüband](#addColorButton)  
  
-   [Hinzufügen eines Farben\-Members zur Dokumentklasse](#addColorMember)  
  
-   [Stifte und Speichern von Einstellungen initialisieren](#initPenSave)  
  
##  <a name="addNewPanel"></a> Hinzufügen von neuen Bereichen zum Menüband  
 Diese Schritte zeigen, wie ein Bereich **Ansicht** hinzufügt, der zwei Kontrollkästchen, die die Sichtbarkeit der Symbolleiste und einer Statusleiste steuern und einen Bereich **Fenster** enthält, der eine vertikal orientierte Trennschaltfläche enthält, die die Erstellung und die Anordnung von MDI \(Multiple Document Interface \(MDI\)\- Fenstern steuert.  
  
#### So fügen Sie ein Ansichts\-Bereich und einem Fensterelement der Menübandleiste hinzufügen  
  
1.  Erstellen Sie einen Bereich erstellt, der mit dem Namen `Ansicht`, der die beiden Kontrollkästchen hat, die die Statusleiste und die Symbolleiste wechseln.  
  
    1.  Ziehen Sie im **WerkzeugkastenBereich**  der Kategorie **Startseite**.  Anschließend ziehen zwei dem Bereich **Kontrollkästchen**.  
  
    2.  Klicken Sie auf den Bereich, um die Eigenschaften zu ändern.  Änderung **Beschriftung** in `Ansicht`.  
  
    3.  Klicken Sie auf das erste Kontrollkästchen, um die Eigenschaften zu ändern.  Ändern Sie **ID** in `ID_VIEW_TOOLBAR` und **Beschriftung** auf `Symbolleiste`.  
  
    4.  Klicken Sie auf das zweite Kontrollkästchen, um die Eigenschaften zu ändern.  Ändern Sie **ID** in `ID_VIEW_STATUS_BAR` und **Beschriftung** auf `Statusleiste`.  
  
2.  Erstellen Sie einen Bereich erstellt, der mit dem Namen `Fenster`, der eine Trennschaltfläche hat.  Wenn ein Benutzer auf die Schaltfläche klickt, unterteilte Kontextmenüanzeige drei Befehle, die bereits in der Scribble\-Anwendung definiert werden.  
  
    1.  Ziehen Sie im **WerkzeugkastenBereich** der Kategorie **Startseite**.  Ziehen Sie **Schaltfläche** im Bereich.  
  
    2.  Klicken Sie auf den Bereich, um die Eigenschaften zu ändern.  Änderung **Beschriftung** in `Fenster`.  
  
    3.  Klicken Sie auf die Schaltfläche.  Ändern Sie **Beschriftung** in `Fenster`, **Schlüssel** auf `w`, die **Large Image Index** auf `1` und **Geteilter Modus** auf `False`.  Klicken Sie anschließend auf die Auslassungspunkte \(**...**\) neben **Menüelemente**, um das Dialogfeld **Elemente\-Editor** zu öffnen.  
  
    4.  Klicken Sie dreimal xxxx 1, drei Schaltflächen hinzuzufügen.  
  
    5.  Klicken Sie auf die erste Schaltfläche und ändern Sie dann **Beschriftung** auf `Neues Fenster` und **ID** auf `ID_WINDOW_NEW`.  
  
    6.  Klicken Sie auf die zweite Schaltfläche und ändern Sie dann **Beschriftung** auf `Überlappend` und **ID** auf `ID_WINDOW_CASCADE`.  
  
    7.  Klicken Sie auf die dritte Schaltfläche und ändern Sie dann **Beschriftung** auf `Nebeneinander` und **ID** auf `ID_WINDOW_TILE_HORZ`.  
  
3.  Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus.  **Ansicht** Und die Bereiche **Fenster** sollten angezeigt werden.  Klicken Sie auf die Schaltflächen, um zu bestätigen, dass diese ordnungsgemäß funktionieren.  
  
 \[[Abschnitte](#top)\]  
  
##  <a name="addHelpPanel"></a> Hinzufügen eines Hilfe\-Bereichs zum Menüband  
 Jetzt können Sie zwei Menüelemente zuweisen, die in der an Menübandschaltflächen Scribble\-Anwendung definiert werden, die **Hilfethemen**  und  **Info** bezeichnet werden.  Die Schaltflächen werden in einem neuen Bereich hinzugefügt, der **Hilfe**.  
  
#### Um einen Hilfebereich hinzufügen  
  
1.  Ziehen Sie im **WerkzeugkastenBereich** der Kategorie **Startseite**.  Anschließend ziehen zwei dem Bereich **Schaltflächen**.  
  
2.  Klicken Sie auf den Bereich, um die Eigenschaften zu ändern.  Änderung **Beschriftung** in `Hilfe`.  
  
3.  Klicken Sie auf die erste Schaltfläche.  Änderung **Beschriftung** in `Hilfethemen` und **ID** auf `ID_HELP_FINDER`.  
  
4.  Klicken Sie auf die zweite Schaltfläche.  Änderung **Beschriftung** in `Übergreifend Scribble...` und **ID** auf `ID_APP_ABOUT`.  
  
5.  Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus.  Ein Bereich **Hilfe**, der zwei Menübandschaltflächen enthält, sollte angezeigt werden.  
  
    > [!IMPORTANT]
    >  Wenn Sie auf die Schaltfläche **Hilfethemen** klicken, öffnet die Scribble\-Anwendung eine komprimierte Hilfe Datei mit dem Namen *your\_project\_name*.chm HTML \(.chm\).  Daher wird das Projekt nicht Scribble genannt wird, müssen Sie die Hilfedatei dem Projektnamen umbenennen.  
  
 \[[Abschnitte](#top)\]  
  
##  <a name="addPenPanel"></a> Hinzufügen eines Stifts\-Bereichs zum Menüband  
 Jetzt fügen Sie einen hinzu Bereich zeigt Schaltflächen an, die die Breite und Farbe des Stiftes steuern.  Dieser Bereich enthält ein Kontrollkästchen, das zwischen die starken und Slim Stifte anzuwenden.  Seine Funktionalität entspricht der des Menüelements in der **Starke Linie** Scribble\-Anwendung.  
  
 Die anfängliche Scribble\-Anwendung können die ausgewählten Stiftsbreiten des Benutzers von einem Dialogfeld, das angezeigt wird, wenn der Benutzer im Menü auf **Stiftbreiten** klickt.  Da die Menübandleiste reichlichen Platz für neue Steuerelemente enthält, können Sie das Dialogfeld Ersetzen, indem Sie beiden Kombinationsfelder auf dem Menüband verwenden.  Ein Kombinationsfeld wird die Breite des Stiftes Slim und andere das Kombinationsfeld wird die Breite des starken Stiftes.  
  
#### Um einen Stift hinzuzufügen Panelobjekt Sie und Kombinationsfelder zum Menüband  
  
1.  Ziehen Sie im **WerkzeugkastenBereich** der Kategorie **Startseite**.  Ziehen Sie **Kontrollkästchen** und **Kombinationsfelder** zwei dem Bereich.  
  
2.  Klicken Sie auf den Bereich, um die Eigenschaften zu ändern.  Änderung **Beschriftung** in `Stift`.  
  
3.  Klicken Sie auf das Kontrollkästchen.  Änderung **Beschriftung** in `Verwendung dick` und **ID** auf `ID_PEN_THICK_OR_THIN`.  
  
4.  Klicken Sie auf das erste Kombinationsfeld.  Änderung **Beschriftung** in `Dünne Stift`, mit **ID** in `ID_PEN_THIN_WIDTH`, für **Text** in `2`, an **Typ** auf `Dropdown-Listenfeld` und für **Daten** in `1; 2; 3; 4; 5; 6; 7; 8; 9;`.  
  
5.  Klicken Sie auf das zweite Kombinationsfeld.  Änderung **Beschriftung** in `Dicker Stift`, mit **ID** in `ID_PEN_THICK_WIDTH`, für **Text** in `5`, an **Typ** auf `Dropdown-Listenfeld` und für **Daten** in `5; 6; 7; 8; 9; 10; 11; 12; 13; 14; 15; 16; 17; 18; 19; 20;`.  
  
6.  Die neuen Kombinationsfelder entsprechen nicht zu allen vorhandenen Menüelemente.  Daher benötigen Sie ein Menüelement für jede Stiftsoption erstellen.  
  
    1.  Im Fenster **Ressourcenansicht** öffnen Sie die IDR\_SCRIBBTYPE\-Menüressource.  
  
    2.  Klicken auf **Stift**, um das p\-Menü **de** zu öffnen.  Klicken Sie auf **Hier eingeben** und geben Sie `Thi &n-Stift` ein.  
  
    3.  Klicken Sie auf den Text, den Sie gerade eingegebenen, um das Fenster **Eigenschaften** zu öffnen, und ändern Sie dann die ID\-Eigenschaft in `ID_PEN_THIN_WIDTH`.  
  
    4.  Sie müssen einen Ereignishandler für jedes Stiftsmenüelement auch erstellen.  Klicken Sie auf das Menüelement **Thi &n\-Stift**, das Sie gerade erstellt haben mit der rechten Maustaste und klicken Sie dann auf **Ereignishandler hinzufügen**.  **Ereignishandler\-Assistent** Wird angezeigt.  
  
    5.  Im Feld **Liste der Klassen** im Assistenten, wählen Sie **CScribbleDoc** aus und klicken dann auf **Hinzu\/Bearb.**.  Daraufhin wird ein Ereignishandler erstellt, die `CScribbleDoc::OnPenThinWidth` genannt wird.  
  
    6.  Fügen Sie `CScribbleDoc::OnPenThinWidth` den folgenden Code hinzu.  
  
        ```  
        // Get a pointer to the ribbon bar  
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();  
        ASSERT_VALID(pRibbon);  
        // Get a pointer to the Thin Width combo box  
        CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(  
           CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THIN_WIDTH));  
        //Get the selected value  
        int nCurSel = pThinComboBox->GetCurSel();  
        if (nCurSel >= 0)  
        {  
           m_nThinWidth = atoi(pThinComboBox->GetItem(nCurSel));  
        }  
        // Create a new pen using the selected width  
        ReplacePen();    
        ```  
  
7.  Fügen Sie ein Menüelement und Ereignishandler für den starken Stift erstellt.  
  
    1.  Im Fenster **Ressourcenansicht** öffnen Sie die IDR\_SCRIBBTYPE\-Menüressource.  
  
    2.  Klicken auf **Stift** , um das Stiftsmenü zu öffnen.  Klicken Sie auf **Hier eingeben** und geben Sie `Thic &k-Stift` ein.  
  
    3.  Klicken Sie auf den folgenden Text Sie \(nur, um das Fenster **Eigenschaften** anzuzeigen mit der rechten Maustaste.  Ändern Sie die ID\-Eigenschaft auf `ID_PEN_THICK_WIDTH`.  
  
    4.  Klicken Sie auf das Menüelement **Dicker Stift**, das Sie gerade erstellt haben mit der rechten Maustaste und klicken Sie dann auf **Ereignishandler hinzufügen**.  **Ereignishandler\-Assistent** Wird angezeigt.  
  
    5.  Im Feld **Liste der Klassen** des Assistenten, wählen Sie **CScribbleDoc** aus und klicken dann auf **Hinzu\/Bearb.**.  Daraufhin wird ein Ereignishandler erstellt, die `CScribbleDoc::OnPenThickWidth` genannt wird.  
  
    6.  Fügen Sie `CScribbleDoc::OnPenThickWidth` den folgenden Code hinzu.  
  
        ```  
        // Get a pointer to the ribbon bar  
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();  
        ASSERT_VALID(pRibbon);  
        CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(  
           CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));  
        // Get the selected value  
        int nCurSel = pThickComboBox->GetCurSel();  
        if (nCurSel >= 0)  
        {  
           m_nThickWidth = atoi(pThickComboBox->GetItem(nCurSel));  
        }  
        // Create a new pen using the selected width  
        ReplacePen();  
        ```  
  
8.  Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus.  Neue Schaltflächen und Kombinationsfelder sollten angezeigt werden.  Versuch mit verschiedenen Stiftsbreiten zu d.  
  
 \[[Abschnitte](#top)\]  
  
##  <a name="addColorButton"></a> Hinzufügen einer Farben\-Schaltfläche zum Stifts\-Bereich  
 Fügen Sie ein [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md)\-Objekt hinzu, das den Benutzer in der Farbe d können.  
  
#### So fügen Sie eine Farbenschaltfläche dem Stiftsbereich hinzufügen  
  
1.  Bevor Sie die Farbenschaltfläche hinzufügen, erstellen Sie ein Menüelement für sie.  Im Fenster **Ressourcenansicht** öffnen Sie die IDR\_SCRIBBTYPE\-Menüressource.  Klicken Sie auf das Menüelement **Stift** , um das Stiftsmenü zu öffnen.  Klicken Sie auf **Hier eingeben** und geben Sie `&Color` ein.  Klicken Sie auf den folgenden Text Sie \(nur, um das Fenster **Eigenschaften** anzuzeigen mit der rechten Maustaste.  Ändern Sie die ID auf `ID_PEN_COLOR`.  
  
2.  Fügen Sie jetzt die Farbenschaltfläche hinzu.  Ziehen Sie im **WerkzeugkastenSchaltfläche "Farbe"** zum Bereich **Stift**.  
  
3.  Klicken Sie auf die Farbenschaltfläche.  Ändern Sie **Beschriftung** in `Farbe`, **ID** auf `ID_PEN_COLOR`, **EinfachAussehen** auf `True`, die **Large Image Index** auf `1` und **Geteilter Modus** auf `False`.  
  
4.  Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus.  Die neue Farbenschaltfläche sollte im Bereich **Stift** angezeigt werden.  Allerdings kann es nicht verwendet werden, da sie noch kein Ereignishandler verfügt.  Die nächsten Schritte zeigen, wie ein Ereignishandler für die Farbenschaltfläche hinzufügt.  
  
 \[[Abschnitte](#top)\]  
  
##  <a name="addColorMember"></a> Hinzufügen eines Farben\-Members zur Dokumentklasse  
 Da die ursprüngliche Scribble\-Anwendung nicht Farbenstifte hat, müssen Sie eine Implementierung für sie schreiben.  Um die Stiftfarbe des Dokuments zu speichern, fügen Sie einen neuen Member der Dokumentklasse, `CscribbleDoc.` hinzugefügt  
  
#### So einem Farbenmember der Dokumentklasse hinzufügen  
  
1.  In scribdoc.h in der `CScribbleDoc`\-Klasse, suchen Sie den Abschnitt `// Attributes`.  Fügen Sie die folgenden Codezeilen nach der Definition des `m_nThickWidth` \- Datenmembers hinzu.  
  
    ```  
    // Current pen color  
    COLORREF   m_penColor;  
    ```  
  
2.  Jedes Dokument enthält eine Liste von schürt, dass der Benutzer bereits gezeichnet hat.  Jeder Strich wird durch ein `CStroke`\-Objekt definiert.  Die `CStroke`\-Klasse enthält keine Informationen über Stiftfarbe.  Daher müssen Sie die Klasse ändern.  In scribdoc.h in der `CStroke`\-Klasse, fügen Sie die folgenden Codezeilen nach der Definition des `m_nPenWidth` \- Datenmembers hinzu.  
  
    ```  
    // Pen color for the stroke  
    COLORREF   m_penColor;  
    ```  
  
3.  In scribdoc.h fügen Sie einen neuen `CStroke`\-Konstruktor hinzu, dessen Parameter einer Breite und einer Farbe angeben.  Fügen Sie die folgende Codezeile nach der `CStroke(UINT nPenWidth);`\-Anweisung hinzu.  
  
    ```  
    CStroke(UINT nPenWidth, COLORREF penColor);  
    ```  
  
4.  In scribdoc.cpp Fügen Sie der Implementierung des neuen Konstruktors `CStroke` hinzu.  Fügen Sie den folgenden Code nach der Implementierung des `CStroke::CStroke(UINT nPenWidth)`\-Konstruktors hinzu.  
  
    ```  
    // Constructor that uses the document's current width and color  
    CStroke::CStroke(UINT nPenWidth, COLORREF penColor)  
    {  
       m_nPenWidth = nPenWidth;  
       m_penColor = penColor;  
       m_rectBounding.SetRectEmpty();  
    }  
    ```  
  
5.  Ändern Sie die zweite Zeile der `CStroke::DrawStroke`\-Methode wie folgt.  
  
    ```  
    if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))  
    ```  
  
6.  Legen Sie die Standardstiftfarbe für die Dokumentklasse fest.  In scribdoc.cpp fügen Sie die folgenden Zeilen `CScribbleDoc::InitDocument`, nach der `m_nThickWidth = 5;`\-Anweisung hinzu.  
  
    ```  
    // default pen color is black  
    m_penColor = RGB(0,0,0);   
    ```  
  
7.  In scribdoc.cpp ändern Sie die erste Zeile der `CScribbleDoc::NewStroke`\-Methode dem folgenden.  
  
    ```  
    CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);  
    ```  
  
8.  Ändern Sie die letzte Zeile der `CScribbleDoc::ReplacePen`\-Methode dem folgenden.  
  
    ```  
    m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);  
    ```  
  
9. Sie haben dem `m_penColor`\-Member in einem vorherigen Schritt hinzugefügt.  Jetzt erstellen Sie einen Ereignishandler für die Farbenschaltfläche erstellt, die den Member festlegen.  
  
    1.  Im Fenster **Ressourcenansicht** öffnen Sie die IDR\_SCRIBBTYPE\-Menüressource.  
  
    2.  Klicken Sie auf das Menüelement **Farbe** mit der rechten Maustaste auf **Ereignishandler hinzufügen…**.  **Ereignishandler\-Assistent** wird angezeigt.  
  
    3.  Im Feld **Liste der Klassen** im Assistenten, wählen Sie **CScribbleDoc** aus und klicken dann auf die Schaltfläche **Hinzu\/Bearb.**.  Dadurch wird der `CScribbleDoc::OnPenColor`\-Ereignishandlerstub erstellt.  
  
10. Ersetzen Sie den Stub für den `CScribbleDoc::OnPenColor`\-Ereignishandler durch folgenden Code.  
  
    ```  
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
  
11. Speichern Sie die Änderungen, erstellen Sie anschließend die Anwendung, und führen Sie sie aus.  Sie sollten in der Lage sein, die Farbenschaltfläche zu drücken und die Farbe des Stiftes zu ändern.  
  
 \[[Abschnitte](#top)\]  
  
##  <a name="initPenSave"></a> Stifte und Speichern von Einstellungen initialisieren  
 Anschließend initialisieren Sie die Farbe und Breite der Stifte.  Schließlich lädt speichern und eine Farbenzeichnung aus einer Datei.  
  
#### Weitere Steuerelemente auf der Menübandleiste initialisieren  
  
1.  Initialisieren Sie die Stifte auf der Menübandleiste.  
  
     Fügen Sie folgenden Code scribdoc.cpp, in der die `CScribbleDoc::InitDocument`\-Methode, nach der `m_sizeDoc = CSize(200,200)`\-Anweisung hinzu.  
  
    ```  
    // Reset the ribbon UI to its initial values  
    CMFCRibbonBar* pRibbon =   
       ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();  
    ASSERT_VALID(pRibbon);  
    CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(  
       CMFCRibbonColorButton,   
       pRibbon->FindByID(ID_PEN_COLOR));  
    // Set ColorButton to black  
    pColorBtn->SetColor(RGB(0,0,0));    
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
  
2.  Speichern Sie eine Farbe, die in einer Datei.  Fügen Sie die folgende Anweisung scribdoc.cpp, in der die `CStroke::Serialize`\-Methode, nach der `ar << (WORD)m_nPenWidth;`\-Anweisung hinzu.  
  
    ```  
    ar << (COLORREF)m_penColor;  
    ```  
  
3.  Schließlich laden Sie eine Farbenzeichnung aus einer Datei.  Fügen Sie die folgende Codezeile, in der die `CStroke::Serialize`\-Methode, nach der `m_nPenWidth = w;`\-Anweisung hinzu.  
  
    ```  
    ar >> m_penColor;  
    ```  
  
4.  Jetzt d Sie farbig und speichern Sie die Zeichnung an eine Datei.  
  
 \[[Abschnitte](#top)\]  
  
## Zusammenfassung  
 Sie haben die MFC\-Scribble\-Anwendung aktualisiert.  Verwenden Sie diese exemplarische Vorgehensweise als Richtlinie, wenn Sie die vorhandenen Anwendungen ändern.  
  
## Siehe auch  
 [Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)   
 [Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble\-Anwendung \(Teil 1\)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)