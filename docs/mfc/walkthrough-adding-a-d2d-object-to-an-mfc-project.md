---
title: "Exemplarische Vorgehensweise: Hinzuf&#252;gen eines D2D-Objekts zu einem MFC-Projekt | Microsoft Docs"
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
  - "D2D [MFC]"
  - "MFC, D2D"
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Exemplarische Vorgehensweise: Hinzuf&#252;gen eines D2D-Objekts zu einem MFC-Projekt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise wird erläutert, wie einem Visual C\+\+\-Projekt vom Typ "Microsoft Foundation Class\-Bibliothek" \(MFC\-Bibliothek\) ein einfaches Direct2D \(D2D\)\-Objekt hinzugefügt und das Projekt anschließend in eine Anwendung eingebunden wird, von der "Hello, World\!" vor einem Hintergrund mit Farbverlauf ausgegeben wird.  
  
 Folgende Aufgaben werden erläutert:  
  
-   Erstellen einer MFC\-Anwendung  
  
-   Erstellen eines Pinsels mit Volltonfarbe und eines Pinsels mit linearem Farbverlauf  
  
-   Ändern des Farbverlaufspinsels, sodass er beim Ändern der Fenstergröße entsprechend angepasst wird  
  
-   Implementieren eines D2D\-Zeichnungshandlers  
  
-   Überprüfen der Ergebnisse  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## Vorbereitungsmaßnahmen  
 Um diese exemplarische Vorgehensweise abzuschließen, müssen Sie Visual Studio.  
  
### So erstellen Sie eine MFC\-Anwendung  
  
1.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  Erweitern Sie im Dialogfeld **Neues Projekt** im linken Bereich unter **Installierte Vorlagen** den Knoten **Visual C\+\+**, und wählen Sie die Option **MFC** aus.  Klicken Sie im mittleren Bereich auf **MFC\-Anwendung**.  Geben Sie im Feld **Name** den Namen `MFCD2DWalkthrough` ein.  Klicken Sie auf **OK**.  
  
3.  Klicken Sie im MFC\-Anwendungs\-Assistenten auf **Fertig stellen**, ohne die Einstellungen zu ändern.  
  
### So erstellen Sie einen Pinsel mit Volltonfarbe und einen Pinsel mit linearem Farbverlauf  
  
1.  Öffnen Sie im Projektmappen\-Explorer im Projekt **MFCD2DWalkthrough** im Ordner **Headerdateien** das Element "MFCD2DWalkthroughView.h".  Fügen Sie der `CMFCD2DWalkthroughView`\-Klasse den folgenden Code hinzu, um drei Datenvariablen zu erstellen:  
  
    ```  
    CD2DTextFormat* m_pTextFormat;  
    CD2DSolidColorBrush* m_pBlackBrush;  
    CD2DLinearGradientBrush* m_pLinearGradientBrush;  
    ```  
  
     Speichern und schließen Sie die Datei.  
  
2.  Öffnen Sie im Ordner **Quelldateien** das Element "MFCD2DWalkthroughView.cpp".  Fügen Sie im Konstruktor für die `CMFCD2DWalkthroughView`\-Klasse den folgenden Code hinzu:  
  
    ```  
    // Enable D2D support for this window:  
    EnableD2DSupport();  
  
    // Initialize D2D resources:  
    m_pBlackBrush = new CD2DSolidColorBrush(GetRenderTarget(), D2D1::ColorF(D2D1::ColorF::Black));  
  
    m_pTextFormat = new CD2DTextFormat(GetRenderTarget(), _T("Verdana"), 50);  
    m_pTextFormat->Get()->SetTextAlignment(DWRITE_TEXT_ALIGNMENT_CENTER);  
    m_pTextFormat->Get()->SetParagraphAlignment(DWRITE_PARAGRAPH_ALIGNMENT_CENTER);  
  
    D2D1_GRADIENT_STOP gradientStops[2];  
  
    gradientStops[0].color = D2D1::ColorF(D2D1::ColorF::White);  
    gradientStops[0].position = 0.f;  
    gradientStops[1].color = D2D1::ColorF(D2D1::ColorF::Indigo);  
    gradientStops[1].position = 1.f;  
  
    m_pLinearGradientBrush = new CD2DLinearGradientBrush(GetRenderTarget(),   
        gradientStops, ARRAYSIZE(gradientStops),  
        D2D1::LinearGradientBrushProperties(D2D1::Point2F(0, 0), D2D1::Point2F(0, 0)));  
    ```  
  
     Speichern und schließen Sie die Datei.  
  
### So ändern Sie den Farbverlaufspinsel, sodass er beim Ändern der Fenstergröße entsprechend angepasst wird  
  
1.  Klicken Sie im Menü **Projekt** auf **Klassen\-Assistent**.  
  
2.  Wählen Sie im MFC\-Klassen\-Assistenten unter **Klassenname** die Option `CMFCD2DWalkthroughView` aus.  
  
3.  Wählen Sie auf der Registerkarte **Meldungen** im Feld **Meldungen** die Option `WM_SIZE` aus, und klicken Sie anschließend auf **Handler hinzufügen**.  Dadurch wird der `OnSize`\-Meldungshandler der `CMFCD2DWalkthroughView`\-Klasse hinzugefügt.  
  
4.  Wählen Sie im Feld **Vorhandene Handler** die Option `OnSize` aus.  Klicken Sie auf **Code bearbeiten**, um die `CMFCD2DWalkthroughView::OnSize`\-Methode anzuzeigen.  Fügen Sie am Ende der Methode den folgenden Code hinzu:  
  
    ```  
    m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));  
    ```  
  
     Speichern und schließen Sie die Datei.  
  
### So implementieren Sie einen D2D\-Zeichnungshandler  
  
1.  Klicken Sie im Menü **Projekt** auf **Klassen\-Assistent**.  
  
2.  Wählen Sie im MFC\-Klassen\-Assistenten unter **Klassenname** die Option `CMFCD2DWalkthroughView` aus.  
  
3.  Klicken Sie auf der Registerkarte **Meldungen** auf **Benutzerdefinierte Meldung hinzufügen**.  
  
4.  Geben Sie im Dialogfeld **Benutzerdefinierte Meldung hinzufügen** im Feld **Benutzerdefinierte Windows\-Meldung** die Zeichenfolge `AFX_WM_DRAW2D` ein.  Geben Sie im Feld **Meldungshandlername** die Zeichenfolge `OnDraw2D` ein.  Wählen Sie die Option **Registrierte Meldung** aus, und klicken Sie anschließend auf **OK**.  Dadurch wird der `CMFCD2DWalkthroughView`\-Klasse ein Meldungshandler für die `AFX_WM_DRAW2D`\-Meldung hinzugefügt.  
  
5.  Wählen Sie im Feld **Vorhandene Handler** die Option `OnDraw2D` aus.  Klicken Sie auf **Code bearbeiten**, um die `CMFCD2DWalkthroughView::OnDraw2D`\-Methode anzuzeigen.  Verwenden Sie den folgenden Code für die `CMFCD2DWalkthroughView::OnDrawD2D`\-Methode:  
  
    ```  
    afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(WPARAM wParam, LPARAM lParam)  
    {  
        CHwndRenderTarget* pRenderTarget = (CHwndRenderTarget*)lParam;  
        ASSERT_VALID(pRenderTarget);  
  
        CRect rect;  
        GetClientRect(rect);  
  
        pRenderTarget->FillRectangle(rect, m_pLinearGradientBrush);  
        pRenderTarget->DrawText(_T("Hello, World!"), rect, m_pBlackBrush, m_pTextFormat);  
  
        return TRUE;  
    }  
    ```  
  
     Speichern und schließen Sie die Datei.  
  
### So überprüfen Sie die Ergebnisse  
  
1.  Erstellen Sie die Anwendung, und führen Sie sie aus.  Ein Rechteck mit Farbverlauf wird angezeigt, das beim Ändern der Fenstergröße angepasst wird. In der Mitte des Rechtecks wird der Text "Hello, World\!" angezeigt.  
  
## Siehe auch  
 [Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)