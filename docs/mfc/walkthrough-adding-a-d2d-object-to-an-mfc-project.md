---
title: 'Exemplarische Vorgehensweise: Hinzufügen eines D2D-Objekts zu einem MFC-Projekt | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7985b36c0eeaa7adf5441a7a6fbb3314bac8353f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>Exemplarische Vorgehensweise: Hinzufügen eines D2D-Objekts zu einem MFC-Projekt
In dieser exemplarischen Vorgehensweise erfahren Sie, wie eine grundlegende Direct2D hinzugefügt (D2D)-Objekt an einer Visual C++-Projekt für Microsoft Foundation Class-Bibliothek (MFC), und erstellen Sie das Projekt in eine Anwendung, die druckt "Hello, World" auf einem Farbverlaufshintergrund.  
  
 Erläutert, wie Sie diese Aufgaben ausführen:  
  
-   Erstellen Sie eine MFC-Anwendung.  
  
-   Erstellen Sie einen Pinsel mit Volltonfarbe und einem linearen Farbverlaufspinsel.  
  
-   Ändern Sie die Farbverlaufspinsel, sodass es entsprechend geändert wird, wenn die Fenstergröße geändert wird.  
  
-   Implementieren Sie einen zeichnen D2D-Handler.  
  
-   Überprüfen Sie die Ergebnisse aus.  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie Visual Studio.  
  
### <a name="to-create-an-mfc-application"></a>Zum Erstellen einer MFC_Anwendung  
  
1.  Zeigen Sie im Menü **Datei** auf **Neu** , und klicken Sie dann auf **Projekt**.  
  
2.  In der **neues Projekt** im Dialogfeld im linken Bereich unter **installierte Vorlagen**, erweitern Sie **Visual C++** und wählen Sie dann **MFC**. Wählen Sie im mittleren Bereich **MFC-Anwendung**. Geben Sie im Feld **Name** `MFCD2DWalkthrough`ein. Klicken Sie auf **OK**.  
  
3.  In der **MFC-Anwendung-Assistent**, klicken Sie auf **Fertig stellen** ohne Änderung von Einstellungen.  
  
### <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>So erstellen einen Pinsel mit Volltonfarbe und einem linearen Farbverlaufspinsel  
  
1.  In **Projektmappen-Explorer**in der **MFCD2DWalkthrough** in-Projekt die **Headerdateien** Ordner öffnen Element "MFCD2DWalkthroughView.h". Fügen Sie folgenden Code, der `CMFCD2DWalkthroughView` Klasse, um drei Datenvariablen zu erstellen.  
  
 ```  
    CD2DTextFormat* m_pTextFormat;  
    CD2DSolidColorBrush* m_pBlackBrush;  
    CD2DLinearGradientBrush* m_pLinearGradientBrush;  
 ```  
  
     Speichern Sie die Datei, und schließen Sie es.  
  
2.  In der **Quelldateien** Ordner öffnen Element "MFCD2DWalkthroughView.cpp". Im Konstruktor für die `CMFCD2DWalkthroughView` Klasse, fügen Sie den folgenden Code hinzu.  
  
 "" * / / D2D-Unterstützung für dieses Fenster aktivieren:  
    EnableD2DSupport();

 * / / D2D-Ressourcen zu initialisieren:  
    M_pBlackBrush = neue CD2DSolidColorBrush(GetRenderTarget(), D2D1::ColorF(D2D1::ColorF::Black));

 
    M_pTextFormat = neue CD2DTextFormat(GetRenderTarget(), _T("Verdana"), 50);

    M_pTextFormat -> Get() SetTextAlignment(DWRITE_TEXT_ALIGNMENT_CENTER); ->

 M_pTextFormat -> Get() SetParagraphAlignment(DWRITE_PARAGRAPH_ALIGNMENT_CENTER); ->

 
    D2D1_GRADIENT_STOP GradientStops [2];  
 
    .color GradientStops [0] = D2D1::ColorF(D2D1::ColorF::White);

    GradientStops [0] .Position ein = 0.f;  
    GradientStops [1] .color = D2D1::ColorF(D2D1::ColorF::Indigo);

    GradientStops [1] .Position ein = 1.f;  
 
    M_pLinearGradientBrush = neue CD2DLinearGradientBrush(GetRenderTarget()   
    GradientStops, ARRAYSIZE(gradientStops),  
    D2D1::LinearGradientBrushProperties (D2D1::Point2F (0, 0), D2D1::Point2F (0, 0)));

 ```  
  
     Save the file and close it.  
  
### To modify the gradient brush so that it will change appropriately when the window is resized  
  
1.  On the **Project** menu, click **Class Wizard**.  
  
2.  In the **MFC Class Wizard**, under **Class name**, select `CMFCD2DWalkthroughView`.  
  
3.  On the **Messages** tab, in the **Messages** box, select `WM_SIZE` and then click **Add Handler**. This action adds the `OnSize` message handler to the `CMFCD2DWalkthroughView` class.  
  
4.  In the **Existing handlers** box, select `OnSize`. Click **Edit Code** to display the `CMFCD2DWalkthroughView::OnSize` method. At the end of the method, add the following code.  
  
 ```  
    M_pLinearGradientBrush -> SetEndPoint (CPoint (Cx, cy));

 ```  
  
     Save the file and close it.  
  
### To implement a D2D drawing handler  
  
1.  On the **Project** menu, click **Class Wizard**.  
  
2.  In the **MFC Class Wizard**, under **Class name**, select `CMFCD2DWalkthroughView`.  
  
3.  On the **Messages** tab, click **Add Custom Message**.  
  
4.  In the **Add Custom Message** dialog box, in the **Custom Windows Message** box, type `AFX_WM_DRAW2D`. In the **Message handler name** box, type `OnDraw2D`. Select the **Registered Message** option and then click **OK**. This action adds a message handler for the `AFX_WM_DRAW2D` message to the `CMFCD2DWalkthroughView` class.  
  
5.  In the **Existing handlers** box, select `OnDraw2D`. Click **Edit Code** to display the `CMFCD2DWalkthroughView::OnDraw2D` method. Use the following code for the `CMFCD2DWalkthroughView::OnDrawD2D` method.  
  
 ```  
    Afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(WPARAM wParam, LPARAM lParam)  
    {  
 CHwndRenderTarget * pRenderTarget = (CHwndRenderTarget *) lParam;  
    ASSERT_VALID(pRenderTarget);

 
    CRect Rect;  
    GetClientRect(rect);

 
    pRenderTarget -> FillRectangle (Rect, M_pLinearGradientBrush);

    pRenderTarget -> DrawText (_T ("Hello, World!"), Rect, M_pBlackBrush, M_pTextFormat);

 
    Geben Sie "true" zurück.  
 }  
 ```  
  
     Save the file and close it.  
  
### To verify the results  
  
1.  Build and run the application. It should have a gradient rectangle that changes when you resize the window. “Hello World!” should be displayed in the center of the rectangle.  
  
## See Also  
 [Walkthroughs](../mfc/walkthroughs-mfc.md)

