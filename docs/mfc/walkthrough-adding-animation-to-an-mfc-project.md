---
title: 'Exemplarische Vorgehensweise: Hinzufügen von Animationen zu einem MFC-Projekt'
ms.date: 09/20/2018
helpviewer_keywords:
- animation [MFC]
- MFC, animation
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
ms.openlocfilehash: 25e29654f1e192e03a078e4a963f27abeea6056d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358603"
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>Exemplarische Vorgehensweise: Hinzufügen von Animationen zu einem MFC-Projekt

In dieser exemplarischen Vorgehensweise erläutert, wie ein Visual C++-Projekt für Microsoft Foundation Class-Bibliothek (MFC) ein einfaches animiertes Objekt hinzugefügt wird.

Die exemplarische Vorgehensweise zeigt, wie folgende Aufgaben ausgeführt wird:

- Erstellen Sie eine MFC-Anwendung.

- Fügen Sie ein Menü "hinzu", und klicken Sie dann die fügen Sie Befehle zum Starten und beenden eine Animation hinzu.

- Erstellen Sie Ereignishandler für die Befehle starten und beenden.

- Fügen Sie dem Projekt ein animiertes Objekt hinzu.

- Das animierte Objekt im Fenster im Mittelpunkt.

- Überprüfen Sie die Ergebnisse aus.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Vorraussetzungen

Um diese exemplarische Vorgehensweise abzuschließen, müssen Sie Visual Studio verfügen.

### <a name="to-create-an-mfc-application"></a>Zum Erstellen einer MFC_Anwendung

1. Zeigen Sie im Menü **Datei** auf **Neu** , und klicken Sie dann auf **Projekt**.

1. In der **neues Projekt** im Dialogfeld im linken Bereich unter **installierte Vorlagen**, erweitern Sie **Visual C++** und wählen Sie dann **MFC**. Wählen Sie im mittleren Bereich **MFC-Anwendung**. In der **Namen** geben *MFCAnimationWalkthrough*. Klicken Sie auf **OK**.

1. In der **MFS-Anwendungsassistenten** Dialogfeld überprüfen Sie, ob **Anwendungstyp** ist **mehrere Dokumente**, **Projektstil** ist **Visual Studio**, und die **Unterstützung für die Dokument-/Ansicht** ausgewählt ist. Klicken Sie auf **Fertig stellen**.

### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>Hinzufügen eines Menüs und Befehle zum Starten und beenden eine Animation hinzufügen

1. Auf der **Ansicht** Startmenü **andere Windows** , und klicken Sie dann auf **Ressourcenansicht**.

1. In **Ressourcenansicht**, navigieren Sie zu der **Menü** Ordner und öffnen Sie sie. Doppelklicken Sie auf die **IDR_MFCAnimationWalkthroughTYPE** Ressource, die sie für die Änderung zu öffnen.

1. Klicken Sie auf der Menüleiste in der **Text hier eingeben** geben *& Imation* zum Erstellen einer Animation-Menüs.

1. Klicken Sie unter **Animation**in die **Text hier eingeben** geben *starten & Vorwärts* zu einen Befehl starten zu erstellen.

1. Klicken Sie unter **vorwärts starten**in die **Text hier eingeben** geben *& rückwärts starten*.

1. Klicken Sie unter **rückwärts starten**in die **Text hier eingeben** geben *Agen & t beenden* erstellen Sie einen Befehl zum Beenden.

1. Speichern Sie MFCAnimationWalkthrough.rc und schließen Sie sie.

1. In **Projektmappen-Explorer**, doppelklicken Sie auf "MainFrm.cpp", um sie für die Änderung zu öffnen. In der `CMainFrame::OnCreate` -Methode, suchen Sie den Abschnitt aus, die mehrere Aufrufe `lstBasicCommands.AddTail`. Fügen Sie den folgenden Code direkt nach diesem Abschnitt.

    ```cpp
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);
    ```

1. Speichern Sie die Datei, und schließen Sie sie.

### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>Erstellen Ereignishandler für das Starten und Beenden von Befehle

1. Auf der **Projekt** Menü klicken Sie auf **-Klassen-Assistent**.

1. In der **MFC-Klassenassistent**unter **Klassenname**Option **CMFCAnimationWalkthroughView**.

1. Auf der **Befehle** Registerkarte die **Objekt-IDs** wählen Sie im **ID_ANIMATION_STARTFORWARD**, und klicken Sie dann in der **Nachrichten** wählen  **Befehl**. Klicken Sie auf **Hinzufügehandlers**.

1. In der **Memberfunktion hinzufügen** Dialogfeld klicken Sie auf **OK**.

1. In der **Objekt-IDs** wählen Sie im **ID_ANIMATION_STARTBACKWARD**, und klicken Sie dann in der **Nachrichten** wählen Sie im **Befehl**. Klicken Sie auf **Hinzufügehandlers**.

1. In der **Memberfunktion hinzufügen** Dialogfeld klicken Sie auf **OK**.

1. In der **Objekt-IDs** wählen Sie im **ID_ANIMATION_STOP**, und klicken Sie dann in der **Nachrichten** wählen Sie im **Befehl**. Klicken Sie auf **Handler hinzufügen** , und klicken Sie dann auf **OK**.

1. In der **Memberfunktion hinzufügen** Dialogfeld klicken Sie auf **OK**.

1. In der **MFC-Klassenassistent**, klicken Sie auf **OK**.

1. Speichern Sie "MFCAnimationWalkthroughView.cpp", die im Editor geöffnet ist, aber schließen Sie es nicht.

### <a name="to-add-an-animated-object-to-the-project"></a>Das Projekt ein animiertes Objekt hinzu

1. In **Projektmappen-Explorer**, doppelklicken Sie auf MFCAnimationWalkthroughView.h, um sie für die Änderung zu öffnen. Unmittelbar vor der Definition der `CMFCAnimationWalkthroughView` -Klasse verwenden, fügen Sie den folgenden Code zum Erstellen eines benutzerdefinierten Animation-Controllers, die Konflikte bei der Planung mit den "Animation"-Objekts behandelt.

    ```cpp
    class CCustomAnimationController : public CAnimationController
    {
    public:
        CCustomAnimationController()
        {
        }

        virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled,
            CAnimationGroup* pGroupNew,
            UI_ANIMATION_PRIORITY_EFFECT priorityEffect)
        {
            return TRUE;
        }
    };
    ```

1. Am Ende der `CMFCAnimationWalkthroughView` Klasse, fügen Sie den folgenden Code hinzu.

    ```cpp
    CCustomAnimationController m_animationController;
    CAnimationColor m_animationColor;
    CAnimationRect m_animationRect;
    ```

1. Nach der `DECLARE_MESSAGE_MAP()` Zeile, fügen Sie den folgenden Code hinzu.

    ```cpp
    void Animate(BOOL bDirection);
    ```

1. Speichern Sie die Datei, und schließen Sie sie.

1. In "MFCAnimationWalkthroughView.cpp" am Anfang der Datei nach der `#include` Anweisungen jedoch vor einer Klasse von Methoden, fügen Sie folgenden Code.

    ```cpp
    static int nAnimationGroup = 0;
    static int nInfoAreaHeight = 40;
    ```

1. Am Ende des Konstruktors für `CMFCAnimationWalkthroughView`, fügen Sie den folgenden Code hinzu.

    ```cpp
    m_animationController.EnableAnimationTimerEventHandler();
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);
    m_animationColor = RGB(255, 255, 255);
    m_animationRect = CRect(0, 0, 0, 0);
    m_animationColor.SetID(-1, nAnimationGroup);
    m_animationRect.SetID(-1, nAnimationGroup);
    m_animationController.AddAnimationObject(&m_animationColor);
    m_animationController.AddAnimationObject(&m_animationRect);
    ```

1. Suchen Sie die `CAnimationWalthroughView::PreCreateWindow` Methode und Ersetzen Sie ihn durch den folgenden Code.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)
    {
        // TODO: Modify the Window class or styles here by modifying
        //       the CREATESTRUCT cs
        m_animationController.SetRelatedWnd(this);

        return CView::PreCreateWindow(cs);
    }
    ```

1. Suchen Sie die `CAnimationWalkthroughView::OnDraw` Methode und Ersetzen Sie ihn durch den folgenden Code.

    ```cpp
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
        strRGB.Format(_T("Fill Color is: %d; %d; %d"),
            GetRValue(m_animationColor),
            GetGValue(m_animationColor),
            GetBValue(m_animationColor));

        dc.DrawText(strRGB, rect, DT_CENTER);
        rect.top += nInfoAreaHeight;

        CBrush br;
        br.CreateSolidBrush(m_animationColor);
        CBrush* pBrushOld = dc.SelectObject(&br);

        dc.Rectangle((CRect)m_animationRect);

        dc.SelectObject(pBrushOld);
    }
    ```

1. Fügen Sie am Ende der Datei den folgenden Code ein.

    ```cpp
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)
    {
        static UI_ANIMATION_SECONDS duration = 3;
        static DOUBLE dblSpeed = 35.;
        static BYTE nStartColor = 50;
        static BYTE nEndColor = 255;

        BYTE nRedColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nGreenColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nBlueColorFinal = bDirection ? nStartColor : nEndColor;

        CLinearTransition* pRedTransition =
            new CLinearTransition(duration, (DOUBLE)nRedColorFinal);

        CSmoothStopTransition* pGreenTransition =
            new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);

        CLinearTransitionFromSpeed* pBlueTransition =
            new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);

        m_animationColor.AddTransition(pRedTransition,
            pGreenTransition,
            pBlueTransition);

        CRect rectClient;
        GetClientRect(rectClient);

        rectClient.top += nInfoAreaHeight;

        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;

        CLinearTransition* pLeftTransition =
            new CLinearTransition(duration, nLeftFinal);

        CLinearTransition* pTopTransition =
            new CLinearTransition(duration, nTopFinal);

        CLinearTransition* pRightTransition =
            new CLinearTransition(duration, nRightFinal);

        CLinearTransition* pBottomTransition =
            new CLinearTransition(duration, nBottomFinal);

        m_animationRect.AddTransition(pLeftTransition,
            pTopTransition,
            pRightTransition,
            pBottomTransition);

        CBaseKeyFrame* pKeyframeStart =
            CAnimationController::GetKeyframeStoryboardStart();
        CKeyFrame* pKeyFrameEnd =
            m_animationController.CreateKeyframe(nAnimationGroup,
                pBlueTransition);

        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);

        m_animationController.AnimateGroup(nAnimationGroup);
    }
    ```

1. Auf der **Projekt** Menü klicken Sie auf **-Klassen-Assistent**.

1. In der **MFC-Klassenassistent**unter **Klassenname**Option **CMFCAnimationWalkthroughView**.

1. Auf der **Nachrichten** Registerkarte die **Nachrichten** Kontrollkästchen **WM_ERASEBKGND**, klicken Sie auf **Handler hinzufügen**, und klicken Sie dann auf **OK** .

1. Ersetzen Sie in "MFCAnimationWalkthroughView.cpp", die Implementierung von `OnEraseBkgnd` durch den folgenden Code, zu reduzieren, in das animierte Objekt Flimmern, wenn es neu gezeichnet wird.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)
    {
        return TRUE;
    }
    ```

1. Ersetzen Sie die Implementierungen der `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward`, und `CMFCAnimationWalkthroughView::OnAnimationStop` durch den folgenden Code.

    ```cpp
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

1. Speichern Sie die Datei, und schließen Sie sie.

### <a name="to-center-the-animated-object-in-the-window"></a>Das animierte Objekt im Fenster zentrieren

1. In **Projektmappen-Explorer**, doppelklicken Sie auf MFCAnimationWalkthroughView.h, um sie für die Änderung zu öffnen. Am Ende der `CMFCAnimationWalkthroughView` -Klasse, nur nach der Definition der `m_animationRect`, fügen Sie den folgenden Code hinzu.

    ```cpp
    BOOL m_bCurrentDirection;
    ```

1. Speichern Sie die Datei, und schließen Sie sie.

1. Auf der **Projekt** Menü klicken Sie auf **-Klassen-Assistent**.

1. In der **MFC-Klassenassistent**unter **Klassenname**Option **CMFCAnimationWalkthroughView**.

1. Auf der **Nachrichten** Registerkarte die **Nachrichten** Kontrollkästchen **WM_SIZE**, klicken Sie auf **Handler hinzufügen**, und klicken Sie dann auf **OK**.

1. Ersetzen Sie in "MFCAnimationWalkthroughView.cpp", den Code für `CMFCAnimationWalkthroughView::OnSize` durch den folgenden Code.

    ```cpp
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

1. Am Anfang des Konstruktors für `CMFCAnimationWalkthroughView`, fügen Sie den folgenden Code hinzu.

    ```cpp
    m_bCurrentDirection = TRUE;
    ```

1. Am Anfang der `CMFCAnimationWalkthroughView::Animate` -Methode, fügen Sie den folgenden Code hinzu.

    ```cpp
    m_bCurrentDirection = bDirection;
    ```

1. Speichern Sie die Datei, und schließen Sie sie.

### <a name="to-verify-the-results"></a>Die Ergebnisse überprüfen

1. Erstellen Sie die Anwendung, und führen Sie sie aus. Auf der **Animation** Menü klicken Sie auf **vorwärts starten**. Ein Rechteck sollte angezeigt werden, und geben Sie dann auf den mittleren Bereich. Beim Klicken auf **rückwärts starten**, wird die Animation umgekehrt und beim Klicken auf **beenden**, beendet werden soll. Die Füllfarbe des Rechtecks sollten wie verläuft die Animation ändern, und die aktuelle Farbe am oberen Rand des Animationsfensters angezeigt werden soll.

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)
