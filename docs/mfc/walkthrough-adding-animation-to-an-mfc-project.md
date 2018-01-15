---
title: "Exemplarische Vorgehensweise: Hinzufügen von Animationen zu einem MFC-Projekt | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- animation [MFC]
- MFC, animation
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f027da0e90bc8dde015c2d42bd72ceb388aa0bba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>Exemplarische Vorgehensweise: Hinzufügen von Animationen zu einem MFC-Projekt
In dieser exemplarischen Vorgehensweise erfahren Sie, wie ein Visual C++-Projekt für Microsoft Foundation Class-Bibliothek (MFC) eine animierte Basisobjekt hinzugefügt.  
  
 Erläutert, wie Sie diese Aufgaben ausführen:  
  
-   Erstellen Sie eine MFC-Anwendung.  
  
-   Fügen Sie ein Menü "hinzu", und fügen Sie dann die Befehle zum Starten und beenden eine Animation.  
  
-   Erstellen Sie Handler für die Start- und Stop-Befehle.  
  
-   Fügen Sie dem Projekt eine animierte Objekt hinzu.  
  
-   Zentrieren Sie das animierte Objekt im Fenster an.  
  
-   Überprüfen Sie die Ergebnisse aus.  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie Visual Studio.  
  
### <a name="to-create-an-mfc-application"></a>Zum Erstellen einer MFC_Anwendung  
  
1.  Zeigen Sie im Menü **Datei** auf **Neu** , und klicken Sie dann auf **Projekt**.  
  
2.  In der **neues Projekt** im Dialogfeld im linken Bereich unter **installierte Vorlagen**, erweitern Sie **Visual C++** und wählen Sie dann **MFC**. Wählen Sie im mittleren Bereich **MFC-Anwendung**. Geben Sie im Feld **Name** `MFCAnimationWalkthrough`ein. Klicken Sie auf **OK**.  
  
3.  In der **MFC-Anwendung-Assistent** Dialogfeld Feld, überprüfen Sie, ob **Anwendungstyp** ist **mehrere Dokumente**, **Projektstil** ist **Visual Studio**, und die **Unterstützung der Dokument-/Ansichtarchitektur** ausgewählt ist. Klicken Sie auf **Fertig stellen**.  
  
### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>Um ein Menü "hinzufügen", und fügen Sie dann die Befehle zum Starten und Beenden einer animation  
  
1.  Auf der **Ansicht** Sie im Menü **Weitere Fenster** , und klicken Sie dann auf **Ressourcenansicht**.  
  
2.  In **Ressourcenansicht**, navigieren Sie zu der **Menü** Ordner, und öffnen Sie es. Doppelklicken Sie auf die `IDR_MFCAnimationWalTYPE` Ressource zu öffnen.  
  
3.  Auf der Menüleiste in der **hier eingeben** geben `A&nimation` eine Animation erstellen.  
  
4.  Klicken Sie unter **Animation**in der **hier eingeben** geben `Start &Forward` So erstellen Sie einen Befehl vorwärts starten.  
  
5.  Klicken Sie unter **vorwärts starten**in der **hier eingeben** geben `Start &Backward`.  
  
6.  Klicken Sie unter **rückwärts starten**in der **hier eingeben** geben `S&top` So erstellen einen Befehl zum Beenden.  
  
7.  Speichern Sie MFCAnimationWalkthrough.rc und schließen Sie es.  
  
8.  In **Projektmappen-Explorer**, doppelklicken Sie auf "MainFrm.cpp", um sie zur Bearbeitung zu öffnen. In der `CMainFrame::OnCreate` -Methode, suchen Sie den Abschnitt aus, die mehrere von Aufrufe `lstBasicCommands.AddTail`. Fügen Sie den folgenden Code unmittelbar nach diesem Abschnitt.  
  
 ```  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);

 lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);

    lstBasicCommands.AddTail(ID_ANIMATION_STOP);

 ```  
  
9. Speichern Sie die Datei, und schließen Sie es.  
  
### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>Zum Erstellen von Handler für das Starten und Beenden Befehle  
  
1.  Auf der **Projekt** Menü klicken Sie auf **Klassen-Assistent**.  
  
2.  In der **MFC-Klassen-Assistent**unter **Klassenname**Option `CMFCAnimationWalkthroughView`.  
  
3.  Auf der **Befehle** Registerkarte die **Objekt-IDs** wählen Sie im `ID_ANIMATION_STARTFORWARD`, und klicken Sie dann in der **Nachrichten** wählen Sie im `COMMAND`. Klicken Sie auf **Hinzufügehandlers**.  
  
4.  In der **Memberfunktion hinzufügen** (Dialogfeld), klicken Sie auf **OK**.  
  
5.  In der **Objekt-IDs** wählen Sie im `ID_ANIMATION_STARTBACKWARD`, und klicken Sie dann in der **Nachrichten** wählen Sie im `COMMAND`. Klicken Sie auf **Hinzufügehandlers**.  
  
6.  In der **Memberfunktion hinzufügen** (Dialogfeld), klicken Sie auf **OK**.  
  
7.  In der **Objekt-IDs** wählen Sie im `ID_ANIMATION_STOP`, und klicken Sie dann in der **Nachrichten** wählen Sie im `COMMAND`. Klicken Sie auf **Handler hinzufügen** , und klicken Sie dann auf **OK**.  
  
8.  In der **Memberfunktion hinzufügen** (Dialogfeld), klicken Sie auf **OK**.  
  
9. In der **MFC-Klassen-Assistent**, klicken Sie auf **OK**.  
  
10. Speichern von "MFCAnimationWalkthroughView.cpp" im Editor geöffnet ist, aber nicht schließen.  
  
### <a name="to-add-an-animated-object-to-the-project"></a>Zum Hinzufügen eines animierten Objekts zum Projekt  
  
1.  Doppelklicken Sie im Projektmappen-Explorer auf MFCAnimationWalkthroughView.h, um sie zur Bearbeitung zu öffnen. Unmittelbar vor der Definition der `CMFCAnimationWalkthroughView` -Klasse verwenden, fügen Sie den folgenden Code aus, um einen benutzerdefinierten Animationscontroller zu erstellen, die Konflikte bei der Planung mit dem Animationsobjekt behandelt.  
  
 ```  
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
  
2.  Am Ende der `CMFCAnimationWalkthroughView` Klasse, fügen Sie den folgenden Code hinzu.  
  
 ```  
    CCustomAnimationController m_animationController;  
    CAnimationColor m_animationColor;   
    CAnimationRect m_animationRect;  
 ```  
  
3.  Nach der `DECLARE_MESSAGE_MAP()` Zeile, fügen Sie den folgenden Code hinzu.  
  
 ```  
    void Animate(BOOL bDirection);

 ```  
  
4.  Speichern Sie die Datei, und schließen Sie es.  
  
5.  In "MFCAnimationWalkthroughView.cpp" am Anfang der Datei hinter den `#include` Anweisungen jedoch vor einer Klasse von Methoden, fügen Sie folgenden Code.  
  
 ```  
    static int nAnimationGroup = 0;  
    static int nInfoAreaHeight = 40;  
 ```  
  
6.  Am Ende des Konstruktors für `CMFCAnimationWalkthroughView`, fügen Sie den folgenden Code hinzu.  
  
 ```  
    m_animationController.EnableAnimationTimerEventHandler();
m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);

 
    m_animationColor = RGB(255,
    255,
    255);

    m_animationRect = CRect(0,
    0,
    0,
    0);

 
    m_animationColor.SetID(-1,
    nAnimationGroup);

    m_animationRect.SetID(-1,
    nAnimationGroup);

 
    m_animationController.AddAnimationObject(&m_animationColor);

 m_animationController.AddAnimationObject(&m_animationRect);

 ```  
  
7.  Suchen Sie die `CAnimationWalthroughView::PreCreateWindow` Methode, und Ersetzen Sie ihn durch den folgenden Code.  
  
 ```  
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)  
 { *// TODO: Modify the Window class or styles here by modifying *//  the CREATESTRUCT cs  
 
    m_animationController.SetRelatedWnd(this);

 return CView::PreCreateWindow(cs);

 }  
 ```  
  
8.  Suchen Sie die `CAnimationWalkthroughView::OnDraw` Methode, und Ersetzen Sie ihn durch den folgenden Code.  
  
 ```  
    void CMFCAnimationWalkthroughView::OnDraw(CDC* pDC)  
 {  
    CMFCAnimationWalkthroughDoc* pDoc = GetDocument();
ASSERT_VALID(pDoc);

 if (!pDoc)  
    return; 
 *// TODO: add draw code for native data here  
    CMemDC dcMem(*pDC,
    this);

    CDC& dc = dcMem.GetDC();

 
    CRect rect;  
    GetClientRect(rect);

 
    dc.FillSolidRect(rect,
    GetSysColor(COLOR_WINDOW));

 
    CString strRGB;  
    strRGB.Format(_T("Fill Color is: %d; %d; %d"),
    GetRValue(m_animationColor),
    GetGValue(m_animationColor),
    GetBValue(m_animationColor));

 
    dc.DrawText(strRGB,
    rect,
    DT_CENTER);

    rect.top += nInfoAreaHeight;  
 
    CBrush br;  
 
    br.CreateSolidBrush(m_animationColor);

 CBrush* pBrushOld = dc.SelectObject(&br);

 
    dc.Rectangle((CRect)m_animationRect);

 dc.SelectObject(pBrushOld);

 }  
 ```  
  
9. Fügen Sie am Ende der Datei den folgenden Code ein.  
  
 ```  
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)  
 {  
    static UI_ANIMATION_SECONDS duration = 3;  
    static DOUBLE dblSpeed = 35.;  
    static BYTE nStartColor = 50;  
    static BYTE nEndColor = 255;  
 
    BYTE nRedColorFinal = bDirection  nStartColor : nEndColor;  
    BYTE nGreenColorFinal = bDirection  nStartColor : nEndColor;  
    BYTE nBlueColorFinal = bDirection  nStartColor : nEndColor;  
 
    CLinearTransition* pRedTransition = new CLinearTransition(duration, (DOUBLE)nRedColorFinal);

    CSmoothStopTransition* pGreenTransition = new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);

    CLinearTransitionFromSpeed* pBlueTransition = new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);

 
    m_animationColor.AddTransition(pRedTransition,
    pGreenTransition,
    pBlueTransition);

 
    CRect rectClient;  
    GetClientRect(rectClient);

 rectClient.top += nInfoAreaHeight;  
 
    int nLeftFinal = bDirection  rectClient.left : rectClient.CenterPoint().x;  
    int nTopFinal = bDirection  rectClient.top : rectClient.CenterPoint().y;  
    int nRightFinal = bDirection  rectClient.right : rectClient.CenterPoint().x;  
    int nBottomFinal = bDirection  rectClient.bottom : rectClient.CenterPoint().y;  
 
    CLinearTransition* pLeftTransition = new CLinearTransition(duration,
    nLeftFinal);

    CLinearTransition* pTopTransition = new CLinearTransition(duration,
    nTopFinal);

    CLinearTransition* pRightTransition = new CLinearTransition(duration,
    nRightFinal);

    CLinearTransition* pBottomTransition = new CLinearTransition(duration,
    nBottomFinal);

 
    m_animationRect.AddTransition(pLeftTransition,
    pTopTransition,
    pRightTransition,
    pBottomTransition);

 
    CBaseKeyFrame* pKeyframeStart = CAnimationController::GetKeyframeStoryboardStart();
CKeyFrame* pKeyFrameEnd = m_animationController.CreateKeyframe(nAnimationGroup,
    pBlueTransition);

 
    pLeftTransition->SetKeyframes(pKeyframeStart,
    pKeyFrameEnd);

    pTopTransition->SetKeyframes(pKeyframeStart,
    pKeyFrameEnd);

    pRightTransition->SetKeyframes(pKeyframeStart,
    pKeyFrameEnd);

    pBottomTransition->SetKeyframes(pKeyframeStart,
    pKeyFrameEnd);

 
    m_animationController.AnimateGroup(nAnimationGroup);

 }  
 ```  
  
10. Auf der **Projekt** Menü klicken Sie auf **Klassen-Assistent**.  
  
11. In der **MFC-Klassen-Assistent**unter **Klassenname**Option `CMFCAnimationWalkthroughView`.  
  
12. Auf der **Nachrichten** Registerkarte die **Nachrichten** wählen Sie im `WM_ERASEBKGND`, klicken Sie auf **Handler hinzufügen**, und klicken Sie dann auf **OK**.  
  
13. Ersetzen Sie in "MFCAnimationWalkthroughView.cpp" die Implementierung von `OnEraseBkgnd` durch den folgenden Code zum Reduzieren des Flackerns in das animierte Objekt, wenn es neu gezeichnet wird.  
  
 ```  
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)  
 {  
    return TRUE;  
 }  
 ```  
  
14. Ersetzen Sie die Implementierungen von `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward`, und `CMFCAnimationWalkthroughView::OnAnimationStop` durch den folgenden Code.  
  
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
  
15. Speichern Sie die Datei, und schließen Sie es.  
  
### <a name="to-center-the-animated-object-in-the-window"></a>Um das animierte Objekt im Fenster zu zentrieren.  
  
1.  In **Projektmappen-Explorer**, doppelklicken Sie auf MFCAnimationWalkthroughView.h, um sie zur Bearbeitung zu öffnen. Am Ende der `CMFCAnimationWalkthroughView` -Klasse direkt nach der Definition der `m_animationRect`, fügen Sie den folgenden Code hinzu.  
  
 ```  
    BOOL m_bCurrentDirection;  
 ```  
  
2.  Speichern Sie die Datei, und schließen Sie es.  
  
3.  Auf der **Projekt** Menü klicken Sie auf **Klassen-Assistent**.  
  
4.  In der **MFC-Klassen-Assistent**unter **Klassenname**Option `CMFCAnimationWalkthroughView`.  
  
5.  Auf der **Nachrichten** Registerkarte die **Nachrichten** wählen Sie im `WM_SIZE`, klicken Sie auf **Handler hinzufügen**, und klicken Sie dann auf **OK**.  
  
6.  Ersetzen Sie in "MFCAnimationWalkthroughView.cpp" den Code für `CMFCAnimationWalkthroughView::OnSize` durch den folgenden Code.  
  
 ```  
    void CMFCAnimationWalkthroughView::OnSize(UINT nType,
    int cx,
    int cy)  
 {  
    CView::OnSize(nType,
    cx,
    cy);

 
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
  
7.  Am Anfang des Konstruktors für `CMFCAnimationWalkthroughView`, fügen Sie den folgenden Code hinzu.  
  
 ```  
    m_bCurrentDirection = TRUE;  
 ```  
  
8.  Am Anfang der `CMFCAnimationWalkthroughView::Animate` -Methode, fügen Sie den folgenden Code hinzu.  
  
 ```  
    m_bCurrentDirection = bDirection;  
 ```  
  
9. Speichern Sie die Datei, und schließen Sie es.  
  
### <a name="to-verify-the-results"></a>Die Ergebnisse überprüfen  
  
1.  Erstellen Sie die Anwendung, und führen Sie sie aus. Auf der **Animation** Menü klicken Sie auf **vorwärts starten**. Ein Rechteck angezeigt werden soll, und geben Sie dann auf den mittleren Bereich. Beim Klicken auf **rückwärts starten**, die Animation umgekehrt und beim Klicken auf **beenden**, beendet werden soll. Die Füllfarbe des Rechtecks im Laufe der Animation ändern sollten, und die aktuelle Farbe am oberen Rand des Animationsfensters angezeigt werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)

