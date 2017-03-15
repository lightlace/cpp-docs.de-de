---
title: "Exemplarische Vorgehensweise: Hinzuf&#252;gen von Animationen zu einem MFC-Projekt | Microsoft Docs"
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
  - "Animation [MFC]"
  - "MFC, Animation"
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Exemplarische Vorgehensweise: Hinzuf&#252;gen von Animationen zu einem MFC-Projekt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise wird erläutert, wie einem Visual C\+\+\-Projekt vom Typ "Microsoft Foundation Class\-Bibliothek" \(MFC\-Bibliothek\) ein einfaches animiertes Objekt hinzugefügt wird.  
  
 Folgende Aufgaben werden erläutert:  
  
-   Erstellen einer MFC\-Anwendung  
  
-   Hinzufügen eines Menüs und anschließendes Hinzufügen von Befehle zum Starten und Beenden einer Animation  
  
-   Erstellen von Handlern für die Befehle zum Starten und Beenden  
  
-   Hinzufügen eines animierten Objekts zum Projekt  
  
-   Zentrieren des animierten Objekts im Fenster  
  
-   Überprüfen der Ergebnisse  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## Vorbereitungsmaßnahmen  
 Um diese exemplarische Vorgehensweise abzuschließen, müssen Sie Visual Studio.  
  
### So erstellen Sie eine MFC\-Anwendung  
  
1.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  Erweitern Sie im Dialogfeld **Neues Projekt** im linken Bereich unter **Installierte Vorlagen** den Knoten **Visual C\+\+**, und wählen Sie die Option **MFC** aus.  Klicken Sie im mittleren Bereich auf **MFC\-Anwendung**.  Geben Sie im Feld **Name** den Namen `MFCAnimationWalkthrough` ein.  Klicken Sie auf **OK**.  
  
3.  Vergewissern Sie sich im Dialogfeld **MFC\-Anwendungs\-Assistent**, dass **Anwendungstyp** auf **Mehrere Dokumente** und **Projektstil** auf **Visual Studio** festgelegt ist. Vergewissern Sie sich außerdem, dass die Unterstützung für die Dokument\-\/Ansichtarchitektur aktiviert ist.  Klicken Sie auf **Fertig stellen**.  
  
### So fügen Sie ein Menü und Befehle zum Starten und Beenden einer Animation hinzu  
  
1.  Zeigen Sie im Menü **Ansicht** auf **Weitere Fenster**, und klicken Sie auf **Ressourcenansicht**.  
  
2.  Navigieren Sie in der Ressourcenansicht zum Ordner **Menü**, und öffnen Sie ihn.  Doppelklicken Sie auf die `IDR_MFCAnimationWalTYPE`\-Ressource, um sie zu öffnen.  
  
3.  Geben Sie auf der Menüleiste im Feld **Hier eingeben**, `A &nimation` ein, um einen Animationsmenüs zu erstellen.  
  
4.  unter **Animation** im Feld **Hier eingeben**, `Starten &Vorwärts` ein, um einen entsprechenden Befehl zu erstellen.  
  
5.  unter **Vorwärts starten** im Feld **Hier eingeben**, `Starten &Rückwärts` ein.  
  
6.  unter **Rückwärts starten** im Feld **Hier eingeben**, `S &oben` ein, um einen Befehl zum Beenden zu erstellen.  
  
7.  Speichern Sie "MFCAnimationWalkthrough.rc", und schließen Sie die Ressource.  
  
8.  Doppelklicken Sie im Projektmappen\-Explorer auf "MainFrm.cpp", um das Element zu öffnen.  Navigieren Sie in der `CMainFrame::OnCreate`\-Methode zu dem Abschnitt, der mehrere Aufrufe von `lstBasicCommands.AddTail` enthält.  Fügen Sie direkt nach diesem Abschnitt den folgenden Code hinzu:  
  
    ```  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);  
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);  
    ```  
  
9. Speichern und schließen Sie die Datei.  
  
### So erstellen Sie Handler für die Befehle zum Starten und Beenden  
  
1.  Klicken Sie im Menü **Projekt** auf **Klassen\-Assistent**.  
  
2.  Wählen Sie im MFC\-Klassen\-Assistenten unter **Klassenname** die Option `CMFCAnimationWalkthroughView` aus.  
  
3.  Wählen Sie auf der Registerkarte **Befehle** im Feld **Objekt\-IDs** die Option `ID_ANIMATION_STARTFORWARD` und im Feld **Meldungen** die Option `COMMAND` aus.  Klicken Sie auf **Handler hinzufügen**.  
  
4.  Klicken Sie im Dialogfeld **Memberfunktion hinzufügen** auf **OK**.  
  
5.  Wählen Sie im Feld **Objekt\-IDs** die Option `ID_ANIMATION_STARTBACKWARD` und im Feld **Meldungen** die Option `COMMAND` aus.  Klicken Sie auf **Handler hinzufügen**.  
  
6.  Klicken Sie im Dialogfeld **Memberfunktion hinzufügen** auf **OK**.  
  
7.  Wählen Sie im Feld **Objekt\-IDs** die Option `ID_ANIMATION_STOP` und im Feld **Meldungen** die Option `COMMAND` aus.  Klicken Sie auf **Handler hinzufügen** und anschließend auf **OK**.  
  
8.  Klicken Sie im Dialogfeld **Memberfunktion hinzufügen** auf **OK**.  
  
9. Klicken Sie im MFC\-Klassen\-Assistenten auf **OK**.  
  
10. Speichern Sie das im Editor geöffnete Element "MFCAnimationWalkthroughView.cpp", aber lassen Sie den Editor geöffnet.  
  
### So fügen Sie dem Projekt ein animiertes Objekt hinzu  
  
1.  Doppelklicken Sie im Projektmappen\-Explorer auf "MFCAnimationWalkthroughView.h", um das Element zu öffnen.  Fügen Sie direkt vor der Definition der `CMFCAnimationWalkthroughView`\-Klasse den folgenden Code hinzu, um einen benutzerdefinierten Animationscontroller zur Behandlung von Planungskonflikten mit dem Animationsobjekt zu erstellen:  
  
    ```  
    class CCustomAnimationController : public CAnimationController  
    {  
    public:  
        CCustomAnimationController()  
        {  
        }  
  
        virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled, CAnimationGroup* pGroupNew, UI_ANIMATION_PRIORITY_EFFECT priorityEffect)  
        {  
            return TRUE;  
        }  
    };  
    ```  
  
2.  Fügen Sie am Ende der `CMFCAnimationWalkthroughView`\-Klasse den folgenden Code hinzu:  
  
    ```  
    CCustomAnimationController m_animationController;  
    CAnimationColor m_animationColor;   
    CAnimationRect m_animationRect;  
    ```  
  
3.  Fügen Sie nach der Zeile `DECLARE_MESSAGE_MAP()` den folgenden Code hinzu:  
  
    ```  
    void Animate(BOOL bDirection);  
    ```  
  
4.  Speichern und schließen Sie die Datei.  
  
5.  Fügen Sie in "MFCAnimationWalkthroughView.cpp" am Dateianfang nach den `#include`\-Anweisungen \(aber noch vor den Klassenmethoden\) den folgenden Code hinzu:  
  
    ```  
    static int nAnimationGroup = 0;  
    static int nInfoAreaHeight = 40;  
    ```  
  
6.  Fügen Sie am Ende des Konstruktors für `CMFCAnimationWalkthroughView` den folgenden Code hinzu:  
  
    ```  
    m_animationController.EnableAnimationTimerEventHandler();  
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);  
  
    m_animationColor = RGB(255, 255, 255);  
    m_animationRect = CRect(0, 0, 0, 0);  
  
    m_animationColor.SetID(-1, nAnimationGroup);  
    m_animationRect.SetID(-1, nAnimationGroup);  
  
    m_animationController.AddAnimationObject(&m_animationColor);  
    m_animationController.AddAnimationObject(&m_animationRect);  
    ```  
  
7.  Navigieren Sie zur `CAnimationWalthroughView::PreCreateWindow`\-Methode, und ersetzen Sie sie durch den folgenden Code:  
  
    ```  
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)  
    {  
        // TODO: Modify the Window class or styles here by modifying  
        //  the CREATESTRUCT cs  
  
        m_animationController.SetRelatedWnd(this);  
        return CView::PreCreateWindow(cs);  
    }  
    ```  
  
8.  Navigieren Sie zur `CAnimationWalkthroughView::OnDraw`\-Methode, und ersetzen Sie sie durch den folgenden Code:  
  
    ```  
    void CMFCAnimationWalkthroughView::OnDraw(CDC* pDC)  
    {  
        CMFCAnimationWalkthroughDoc* pDoc = GetDocument();  
        ASSERT_VALID(pDoc);  
        if (!pDoc)  
            return;  
  
        // TODO: add draw code for native data here  
        CMemDC dcMem(*pDC, this);  
        CDC& dc = dcMem.GetDC();  
  
        CRect rect;  
        GetClientRect(rect);  
  
        dc.FillSolidRect(rect, GetSysColor(COLOR_WINDOW));  
  
        CString strRGB;  
        strRGB.Format(_T("Fill Color is: %d; %d; %d"), GetRValue(m_animationColor), GetGValue(m_animationColor), GetBValue(m_animationColor));  
  
        dc.DrawText(strRGB, rect, DT_CENTER);  
        rect.top += nInfoAreaHeight;  
  
        CBrush br;  
  
        br.CreateSolidBrush(m_animationColor);  
        CBrush* pBrushOld = dc.SelectObject(&br);  
  
        dc.Rectangle((CRect)m_animationRect);  
        dc.SelectObject(pBrushOld);  
    }  
    ```  
  
9. Fügen Sie am Ende der Datei den folgenden Code hinzu:  
  
    ```  
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)  
    {  
        static UI_ANIMATION_SECONDS duration = 3;  
        static DOUBLE dblSpeed = 35.;  
        static BYTE nStartColor = 50;  
        static BYTE nEndColor = 255;  
  
        BYTE nRedColorFinal = bDirection ? nStartColor : nEndColor;  
        BYTE nGreenColorFinal = bDirection ? nStartColor : nEndColor;  
        BYTE nBlueColorFinal = bDirection ? nStartColor : nEndColor;  
  
        CLinearTransition* pRedTransition = new CLinearTransition(duration, (DOUBLE)nRedColorFinal);  
        CSmoothStopTransition* pGreenTransition = new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);  
        CLinearTransitionFromSpeed* pBlueTransition = new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);  
  
        m_animationColor.AddTransition(pRedTransition, pGreenTransition, pBlueTransition);  
  
        CRect rectClient;  
        GetClientRect(rectClient);  
        rectClient.top += nInfoAreaHeight;  
  
        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;  
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;  
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;  
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;  
  
        CLinearTransition* pLeftTransition = new CLinearTransition(duration, nLeftFinal);  
        CLinearTransition* pTopTransition = new CLinearTransition(duration, nTopFinal);  
        CLinearTransition* pRightTransition = new CLinearTransition(duration, nRightFinal);  
        CLinearTransition* pBottomTransition = new CLinearTransition(duration, nBottomFinal);  
  
        m_animationRect.AddTransition(pLeftTransition, pTopTransition, pRightTransition, pBottomTransition);  
  
        CBaseKeyFrame* pKeyframeStart = CAnimationController::GetKeyframeStoryboardStart();  
        CKeyFrame* pKeyFrameEnd = m_animationController.CreateKeyframe(nAnimationGroup, pBlueTransition);  
  
        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
  
        m_animationController.AnimateGroup(nAnimationGroup);  
    }  
    ```  
  
10. Klicken Sie im Menü **Projekt** auf **Klassen\-Assistent**.  
  
11. Wählen Sie im MFC\-Klassen\-Assistenten unter **Klassenname** die Option `CMFCAnimationWalkthroughView` aus.  
  
12. Wählen Sie auf der Registerkarte **Meldungen** im Feld **Meldungen** die Option `WM_ERASEBKGND` aus, klicken Sie auf **Handler hinzufügen**, und klicken Sie anschließend auf **OK**.  
  
13. Ersetzen Sie in "MFCAnimationWalkthroughView.cpp" die Implementierung von `OnEraseBkgnd` durch den folgenden Code, um das Flimmern des animierten Objekts beim Neuzeichnen zu verringern:  
  
    ```  
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)  
    {  
        return TRUE;  
    }  
    ```  
  
14. Ersetzen Sie die Implementierungen von `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward` und `CMFCAnimationWalkthroughView::OnAnimationStop` durch den folgenden Code:  
  
    ```  
    void CMFCAnimationWalkthroughView::OnAnimationStartforward()  
    {  
        Animate(TRUE);  
    }  
  
    void CMFCAnimationWalkthroughView::OnAnimationStartbackward()  
    {  
        Animate(FALSE);  
    }  
  
    void CMFCAnimationWalkthroughView::OnAnimationStop()  
    {  
        IUIAnimationManager* pManager = m_animationController.GetUIAnimationManager();  
        if (pManager != NULL)  
        {  
            pManager->AbandonAllStoryboards();  
        }  
    }  
  
    ```  
  
15. Speichern und schließen Sie die Datei.  
  
### So zentrieren Sie das animierte Objekt im Fenster  
  
1.  Doppelklicken Sie im Projektmappen\-Explorer auf "MFCAnimationWalkthroughView.h", um das Element zu öffnen.  Fügen Sie am Ende der `CMFCAnimationWalkthroughView`\-Klasse direkt nach der Definition von `m_animationRect` den folgenden Code hinzu:  
  
    ```  
    BOOL m_bCurrentDirection;  
    ```  
  
2.  Speichern und schließen Sie die Datei.  
  
3.  Klicken Sie im Menü **Projekt** auf **Klassen\-Assistent**.  
  
4.  Wählen Sie im MFC\-Klassen\-Assistenten unter **Klassenname** die Option `CMFCAnimationWalkthroughView` aus.  
  
5.  Wählen Sie auf der Registerkarte **Meldungen** im Feld **Meldungen** die Option `WM_SIZE` aus, klicken Sie auf **Handler hinzufügen**, und klicken Sie anschließend auf **OK**.  
  
6.  Ersetzen Sie in "MFCAnimationWalkthroughView.cpp" den Code für `CMFCAnimationWalkthroughView::OnSize` durch den folgenden Code:  
  
    ```  
    void CMFCAnimationWalkthroughView::OnSize(UINT nType, int cx, int cy)  
    {  
        CView::OnSize(nType, cx, cy);  
  
        CRect rect;  
        GetClientRect(rect);  
        rect.top += nInfoAreaHeight;  
  
        CRect rectAnim = m_animationRect;  
        m_animationRect = CRect(CPoint(rect.CenterPoint().x - rectAnim.Width() / 2,   
                                rect.CenterPoint().y - rectAnim.Height() / 2),   
                                rectAnim.Size());  
  
        if (m_animationController.IsAnimationInProgress())  
        {  
            Animate(m_bCurrentDirection);  
        }  
    }  
    ```  
  
7.  Fügen Sie am Anfang des Konstruktors für `CMFCAnimationWalkthroughView` den folgenden Code hinzu:  
  
    ```  
    m_bCurrentDirection = TRUE;  
    ```  
  
8.  Fügen Sie am Anfang der `CMFCAnimationWalkthroughView::Animate`\-Methode den folgenden Code hinzu:  
  
    ```  
    m_bCurrentDirection = bDirection;  
    ```  
  
9. Speichern und schließen Sie die Datei.  
  
### So überprüfen Sie die Ergebnisse  
  
1.  Erstellen Sie die Anwendung, und führen Sie sie aus.  Klicken Sie im Menü **Animation** auf **Vorwärts starten**.  Ein Rechteck wird angezeigt und füllt den mittleren Bereich aus.  Wenn Sie auf **Rückwärts starten** klicken, wird die Animation umgekehrt. Durch Klicken auf **Beenden** wird die Animation beendet.  Die Füllfarbe des Rechtecks ändert sich im Laufe der Animation, und die aktuelle Farbe wird am oberen Rand des Animationsfensters angezeigt.  
  
## Siehe auch  
 [Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)