---
title: CMFCOutlookBar-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar::AllowDestroyEmptyTabbedPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanAcceptPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanSetCaptionTextToTabName
- AFXOUTLOOKBAR/CMFCOutlookBar::Create
- AFXOUTLOOKBAR/CMFCOutlookBar::CreateCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::DoesAllowDynInsertBefore
- AFXOUTLOOKBAR/CMFCOutlookBar::FloatTab
- AFXOUTLOOKBAR/CMFCOutlookBar::GetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::GetTabArea
- AFXOUTLOOKBAR/CMFCOutlookBar::IsMode2003
- AFXOUTLOOKBAR/CMFCOutlookBar::OnAfterAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnBeforeAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnScroll
- AFXOUTLOOKBAR/CMFCOutlookBar::RemoveCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::SetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::SetMode2003
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBar [MFC], AllowDestroyEmptyTabbedPane
- CMFCOutlookBar [MFC], CanAcceptPane
- CMFCOutlookBar [MFC], CanSetCaptionTextToTabName
- CMFCOutlookBar [MFC], Create
- CMFCOutlookBar [MFC], CreateCustomPage
- CMFCOutlookBar [MFC], DoesAllowDynInsertBefore
- CMFCOutlookBar [MFC], FloatTab
- CMFCOutlookBar [MFC], GetButtonsFont
- CMFCOutlookBar [MFC], GetTabArea
- CMFCOutlookBar [MFC], IsMode2003
- CMFCOutlookBar [MFC], OnAfterAnimation
- CMFCOutlookBar [MFC], OnBeforeAnimation
- CMFCOutlookBar [MFC], OnScroll
- CMFCOutlookBar [MFC], RemoveCustomPage
- CMFCOutlookBar [MFC], SetButtonsFont
- CMFCOutlookBar [MFC], SetMode2003
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ed3a07b7994d2c7adc7a5d708d31abe9c49437f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717105"
---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar-Klasse
Eine Seite im Registerformat mit dem Aussehen des **Navigationsbereichs** in Microsoft Outlook 2000 oder Outlook 2003. Die `CMFCOutlookBar` Objekt enthält eine [CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md) Objekt und eine Reihe von Registerkarten. Die Registerkarten können es sich um [CMFCOutlookBarPane-Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md) Objekte oder `CWnd`--abgeleitete Objekte. Für den Benutzer wird die Outlook-Leiste in Form einer Reihe von Schaltflächen und eines Anzeigebereichs dargestellt. Wenn der Benutzer auf eine Schaltfläche klickt, wird der entsprechende Steuerelement- oder Schaltflächenbereich angezeigt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCOutlookBar::CMFCOutlookBar`|Standardkonstruktor|  
|`CMFCOutlookBar::~CMFCOutlookBar`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Gibt an, ob es sich bei einem leeren Bereich im Registerkartenformat zerstört werden kann. (Überschreibt [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|  
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Bestimmt, ob ein weiterer Bereich, um die Outlook-Leistenbereich angedockt werden kann. (Überschreibt CDockablePane::CanAcceptPane.)|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Bestimmt, ob die Beschriftung für die Seite im Registerformat mit den gleichen Text als aktive Registerkarte angezeigt. (Überschreibt [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|  
|[CMFCOutlookBar::Create](#create)|Die Outlook-Leistensteuerelement wird erstellt.|  
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Erstellt eine benutzerdefinierte Registerkarte des Outlook-Leiste.|  
|`CMFCOutlookBar::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Bestimmt, ob ein Benutzer eine Steuerleiste am äußeren Rand der Outlook-Leiste angedockt werden kann.|  
|[CMFCOutlookBar::FloatTab](#floattab)|Hebt die Verankerung eines Bereichs auf, aber nur, wenn der Bereich sich auf einer lösbaren Registerkarte befindet. (Überschreibt [cbasetabbedpane:: Floattab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Gibt die Schriftart des Texts auf den Schaltflächen der Outlook-Leiste zurück.|  
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Gibt die Größe und Position der Bereiche Registerkarte in der Outlook-Leiste zurück. (Überschreibt [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|  
|`CMFCOutlookBar::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Bestimmt, ob das Verhalten der Outlook-Leiste, die von Microsoft Office Outlook 2003 imitiert (siehe Hinweise).|  
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|Wird aufgerufen, indem [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) nachdem die aktive Registerkarte mit der Animation festgelegt wurde.|  
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|Wird aufgerufen, indem [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) vor einer Registerkarte Seite als aktive Registerkarte mit der Animation festgelegt ist.|  
|[CMFCOutlookBar::OnScroll](#onscroll)|Vom Framework aufgerufen, wenn die Outlook-Leiste einen nach oben oder unten Bildlauf.|  
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Entfernt eine benutzerdefinierte Registerkarte des Outlook-Leiste.|  
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Legt die Schriftart des Texts für die Schaltflächen der Outlook-Leiste fest.|  
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Gibt an, ob das Verhalten der Outlook-Leiste, die von Outlook 2003 imitiert (siehe Hinweise).|  
  
## <a name="remarks"></a>Hinweise  
 Ein Beispiel für eine Outlook-Leiste, finden Sie unter den [OutlookDemo-Beispiel: MFC-Anwendung für OutlookDemo](../../visual-cpp-samples.md).  
  
## <a name="implementing-the-outlook-bar"></a>Implementieren die Outlook-Leiste  
 Befolgen Sie folgende Schritte, um das `CMFCOutlookBar`-Steuerelement in Ihrer Anwendung zu verwenden:  
  
1.  Betten Sie ein `CMFCOutlookBar`-Objekt in die Hauptframe-Fensterklasse ein.  
  
    ```cpp
    class CMainFrame : public CMDIFrameWnd  
    { 
        // ...  
        CMFCOutlookBar m_wndOutlookBar;  
        CMFCOutlookBarPane m_wndOutlookPane;  
        // ...
    };  
    ```

2.  Wenn Sie die WM_CREATE-Nachricht in die Hauptframe zu verarbeiten, rufen die [CMFCOutlookBar::Create](#create) Methode, um die Outlook-Leiste Registerkarten-Steuerelement zu erstellen.  
  
    ```cpp
    m_wndOutlookBar.Create (_T("Shortcuts"),
        this,
        CRect (0, 0, 100, 100),
        ID_VIEW_OUTLOOKBAR,
        WS_CHILD | WS_VISIBLE | CBRS_LEFT);
    ```

3.  Abrufen eines Zeigers auf den zugrunde liegenden `CMFCOutlookBarTabCtrl` mit [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow).  
  
    ```cpp
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();
    ```
    
4.  Erstellen Sie eine [CMFCOutlookBarPane-Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md) -Objekt für jede Registerkarte, auf die Schaltflächen enthält.  
  
    ```cpp
    m_wndOutlookPane.Create(&m_wndOutlookBar,
        AFX_DEFAULT_TOOLBAR_STYLE,
        ID_OUTLOOK_PANE_GENERAL,
        AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);  

    // make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking(CBRS_ALIGN_ANY);

    // add buttons  
    m_wndOutlookPane.AddButton(theApp.LoadIcon (IDR_MAINFRAME),
        "About",
        ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON),
        "Open",
        ID_FILE_OPEN);
    ```

5.  Rufen Sie [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) jedes neue Registerkarte hinzufügen. Legen Sie die *bDetachable* Parameter auf "false", um eine Seite nicht entfernbar machen. Oder verwenden Sie [CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) entfernbare Seiten hinzufügen.  
  
    ```cpp
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);
    ```  

6.  Hinzufügen einer `CWnd`-abgeleiteten Steuerelements (z. B. [CMFCShellTreeCtrl-Klasse](../../mfc/reference/cmfcshelltreectrl-class.md)) als Registerkarte, zu erstellen, das Steuerelement, und rufen [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) So fügen sie die Outlook-Leiste hinzu.  
  
> [!NOTE]
>  Befolgen Sie für jeden eindeutigen Steuerelement-IDs [CMFCOutlookBarPane-Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md) Objekt und für jede `CWnd`-abgeleitetes Objekt.  
  
 Verwenden Sie dynamisch hinzufügen oder löschen die neue Seiten zur Laufzeit, [CMFCOutlookBar::CreateCustomPage](#createcustompage) und [CMFCOutlookBar::RemoveCustomPage](#removecustompage).  
  
## <a name="outlook-2003-mode"></a>Outlook 2003-Modus  
 In Outlook 2003-Modus werden die Schaltflächen auf die Registerkarte am unteren Rand der Outlook-Leistenbereich positioniert. Wenn nicht ausreichend Platz zur Anzeige der Schaltflächen vorhanden ist, werden sie als Symbole in einem Bereich symbolleistenähnlicher am unteren Rand des Bereichs angezeigt.  
  
 Verwendung [CMFCOutlookBar::SetMode2003](#setmode2003) Outlook 2003-Modus zu aktivieren. Verwendung [CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) Bitmap festlegen, die die Symbole enthält, die am unteren Rand der Outlook-Leiste angezeigt werden. Die Symbole in die Bitmap müssen nach Registerkartenindex sortiert werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxoutlookbar.h  
  
##  <a name="allowdestroyemptytabbedpane"></a>  CMFCOutlookBar::AllowDestroyEmptyTabbedPane  
 Gibt an, ob es sich bei einem leeren Bereich im Registerkartenformat zerstört werden kann.  
  
```cpp  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn Sie einen leeren Bereich im Registerkartenformat zerstört werden kann. andernfalls "false". Immer die Standardimplementierung gibt "true" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen leeren Bereich im Registerkartenformat kann nicht gelöscht werden soll, wird Sie in das Framework stattdessen ausgeblendet.  
  
##  <a name="canacceptpane"></a>  CMFCOutlookBar::CanAcceptPane  
 Bestimmt, ob ein weiterer Bereich, um die Outlook-Leistenbereich angedockt werden kann.  
  
```cpp  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
*pBar*<br/>
[in] Ein Zeiger auf einen anderen Bereich, der in diesen Bereich angedockt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn ein weiterer Bereich, um die Outlook-Leistenbereich angedockt werden kann. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Outlook-Leiste in Outlook 2003-Modus, Andocken ist nicht unterstützt wird, daher ist der Rückgabewert "false".  
  
 Wenn die *pBar* Parameter NULL ist, gibt diese Methode FALSE zurück.  
  
 Diese Methode verhält sich andernfalls, wie die Basismethode [cbasepane:: Canacceptpane](../../mfc/reference/cbasepane-class.md#canacceptpane), außer dass selbst wenn das Andocken nicht aktiviert ist, ist eine Outlook-Leiste kann immer noch einem anderen Outlook-Leiste darüber angedockt werden.  
  
##  <a name="cansetcaptiontexttotabname"></a>  CMFCOutlookBar::CanSetCaptionTextToTabName  
 Bestimmt, ob die Beschriftung für die Seite im Registerformat mit den gleichen Text als aktive Registerkarte angezeigt.  
  
```cpp  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Outlook-Leiste der Titel des Fensters auf den Text der aktiven Registerkarte automatisch festgelegt wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) aktivieren oder deaktivieren diese Funktionalität.  
  
 Im Modus für Outlook 2003 ist diese Einstellung immer aktiviert.  
  
##  <a name="create"></a>  CMFCOutlookBar::Create  
 Die Outlook-Leistensteuerelement wird erstellt.  
  
```cpp  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwControlBarStyle=AFX_CBRS_RESIZE,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Parameter  
*lpszCaption*<br/>
[in] Gibt an, die fensterbeschriftung.  
  
*pParentWnd*<br/>
[in] Gibt einen Zeiger auf ein übergeordnetes Fenster. Es darf nicht NULL sein.  
  
*Rect*<br/>
[in] Gibt an, die Outlook-Leiste Größe und Position in Pixel.  
  
*nID*<br/>
[in] Gibt an, die Steuerelement-ID. Muss sich von anderen Steuerelement-IDs, die in der Anwendung verwendet werden.  
  
*dwStyle*<br/>
[in] Gibt das gewünschte Steuerelement Standardstil der Statusleiste an. Mögliche Werte finden Sie unter [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
*dwControlBarStyle*<br/>
[in] Gibt an, die besondere Bibliothek definierten Stile.  
  
*"pContext"*<br/>
[in] Erstellen von Kontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CMFCOutlookBar` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor, und rufen Sie dann `Create`, die den Outlook-Leistensteuerelement erstellt, und fügt es der `CMFCOutlookBar` Objekt.  
  
 Finden Sie unter [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex) für die Liste der verfügbaren Bibliothek definierte Formatvorlagen durch festzulegende *DwControlBarStyle*.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` Methode der `CMFCOutlookBar` Klasse. Dieser Codeausschnitt ist Teil der [Outlook mit mehreren Ansichten Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]  
  
##  <a name="createcustompage"></a>  CMFCOutlookBar::CreateCustomPage  
 Erstellt eine benutzerdefinierte Registerkarte des Outlook-Leiste.  
  
```cpp  
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,  
    BOOL bActivatePage=TRUE,  
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,  
    BOOL bEnableTextLabels=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*lpszPageName*<br/>
[in] Die Beschriftung "".  
  
*bActivatePage*<br/>
[in] Wenn TRUE, wird die Seite bei der Erstellung aktiviert.  
  
*dwEnabledDocking*<br/>
[in] Eine Kombination von CBRS_ALIGN_-Flags, die angibt, die aktiviert Andocken Seiten auf, wenn die Seite getrennt wird.  
  
*bEnableTextLabels*<br/>
[in] Wenn TRUE, sind die Bezeichnungen für die Schaltflächen aktiviert, die sich auf der Seite befinden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Seite oder NULL, wenn die Erstellung ist fehlgeschlagen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Benutzer zum Erstellen benutzerdefinierter Outlook-Leiste Seiten zu ermöglichen. Sie können bis zu 100 Seiten pro Anwendung erstellen. Das Seitensteuerelement starten IDs von "0xf000". Die Erstellung schlägt fehl, wenn die Gesamtzahl der Seiten, die benutzerdefinierte Outlook-Leiste 100 überschreitet.  
  
 Verwendung [CMFCOutlookBar::RemoveCustomPage](#removecustompage) zum Löschen von benutzerdefinierter Seiten.  
  
##  <a name="doesallowdyninsertbefore"></a>  CMFCOutlookBar::DoesAllowDynInsertBefore  
 Gibt an, ob ein Benutzer einen Bereich am äußeren Rand der Outlook-Leiste angedockt werden kann.  
  
```  
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt "false" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework Ruft die `DoesAllowDynInsertBefore` Methode, wenn sie einen Speicherort für einen dynamischen Bereich anzudocken aussieht. Wenn die Funktion "false" zurückgibt, lässt das Framework nicht das Andocken der jeder Bereich für dynamische an den äußeren Kanten des Bereichs.  
  
 In der Regel erstellen Sie eine Outlook-Leiste als statische unverankerte-Steuerelement. Sie können diese Funktion in einer abgeleiteten Klasse überschreiben und gibt "true", um dieses Verhalten zu ändern.  
  
> [!NOTE]
>  Da dynamische Bereiche den Status des angedockten statische Bereiche überprüfen, wenn andocken, sollten Sie dynamische Bereiche nach statischen Bereichen möglichst andocken.  
  
##  <a name="floattab"></a>  CMFCOutlookBar::FloatTab  
 Wird einen Bereich verschoben.  
  
```cpp  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>Parameter  
*pBar*<br/>
[in] Ein Zeiger auf den Bereich, um "float".  
  
*nTabID*<br/>
[in] Der nullbasierte Index der Registerkarte "float".  
  
*dockMethod*<br/>
[in] Gibt die Methode zu verwenden, um den Bereich "float".  Weitere Informationen finden Sie unter [cbasetabbedpane:: Floattab](../../mfc/reference/cbasetabbedpane-class.md#floattab).  
  
*bHide*<br/>
[in] True, um den Bereich ausblenden, bevor Sie die floating. andernfalls "false". Im Gegensatz zu die Basisklassenversion dieser Methode ist dieser Parameter keinen Standardwert aufweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich abgedockt. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entspricht [cbasetabbedpane:: Floattab](../../mfc/reference/cbasetabbedpane-class.md#floattab) mit dem Unterschied, dass sie nicht die letzte verbleibende-Registerkarte auf eine Outlook-Leistensteuerelement, "float" unterstützt.  
  
##  <a name="getbuttonsfont"></a>  CMFCOutlookBar::GetButtonsFont  
 Gibt die Schriftart des Texts auf der Seite-Schaltfläche Registerkarten der Outlook-Leiste zurück.  
  
```cpp  
CFont* GetButtonsFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Schriftartobjekt, das zum Anzeigen von Text in Outlook Leiste Registerkarten für Seiten-Schaltfläche verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Schriftart abzurufen, die verwendet wird, um den Text auf Outlook-Schaltfläche Seitenregisterkarten anzuzeigen. Sie können die Schriftart festlegen, durch den Aufruf auf [CMFCOutlookBar::SetButtonsFont](#setbuttonsfont).  
  
##  <a name="gettabarea"></a>  CMFCOutlookBar::GetTabArea  
 Bestimmt die Größe und Position der Bereiche Registerkarte in der Outlook-Leiste.  
  
```cpp  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parameter  
*rectTabAreaTop*<br/>
[out] Enthält die Größe und Position (in Clientkoordinaten) des Bereichs, Registerkarte "Top", bei Rückgabe der Funktion.  
  
*rectTabAreaBottom*<br/>
[out] Enthält die Größe und Position (in Clientkoordinaten) des Registerkartenbereichs unten an, bei Rückgabe der Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um den Typ auf den Bereich "Ziel" Andocken zu bestimmen. Wenn das Framework feststellt, dass der Benutzer den Bereich, um über den Registerkartenbereich im Ziel-Bereich angedockt werden zieht, versucht, den ersten Bereich als eine neue Registerkarte, der den Bereich "Ziel" hinzufügen. Andernfalls versucht, den ersten Bereich einen entsprechenden auf der der Bereich "Ziel" andocken. Das Framework erstellt einen neuen Container mit einem Schieberegler, um den zusätzlichen angedockten Bereich zu berücksichtigen.  
  
 Die standardmäßige Implementierung des `GetTabArea` gibt den gesamten Clientbereich der Outlook-Leiste zurück, wenn die Outlook-Leiste statische; ist, ist, wenn die Outlook-Leiste "float" kann nicht. Andernfalls wird den Bereich, den Schaltflächen am oberen und unteren Rand des Steuerelements der Outlook-Leiste werden zurückgegeben.  
  
 Diese Methode in der abgeleiteten Klasse überschreiben `CMFCOutlookBar` , dieses Verhalten ändern.  
  
##  <a name="ismode2003"></a>  CMFCOutlookBar::IsMode2003  
 Gibt an, ob das Verhalten der Outlook-Leiste, die von Microsoft Office Outlook 2003 imitiert.  
  
```cpp  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Outlook-Leiste im Microsoft Office 2003-Modus ausgeführt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diesen Modus aktivieren, indem Sie mithilfe von [CMFCOutlookBar::SetMode2003](#setmode2003).  
  
##  <a name="onafteranimation"></a>  CMFCOutlookBar::OnAfterAnimation  
 Wird aufgerufen, indem [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) nachdem die aktive Registerkarte mit der Animation festgelegt wurde.  
  
```cpp  
virtual void OnAfterAnimation(int nPage);
```  
  
### <a name="parameters"></a>Parameter  
*. nSeite*<br/>
[in] Der nullbasierte Index der Registerkarte, die aktiven vorgenommen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Der visuelle Effekt der aktive Registerkarte festlegen, hängt davon ab, ob Sie die Animation aktiviert haben. Weitere Informationen finden Sie unter [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).  
  
##  <a name="onbeforeanimation"></a>  CMFCOutlookBar::OnBeforeAnimation  
 Wird aufgerufen, indem [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) vor einer Registerkarte Seite als aktive Registerkarte mit der Animation festgelegt ist.  
  
```cpp  
virtual BOOL OnBeforeAnimation(int nPage);
```  
  
### <a name="parameters"></a>Parameter  
*. nSeite*<br/>
[in] Der nullbasierte Index der Registerkarte, die aktiv festgelegt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt zurück, TRUE, wenn die Animation beim Festlegen der neuen aktiven Registerkarte verwendet werden soll, oder FALSE, wenn die Animation deaktiviert werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onscroll"></a>  CMFCOutlookBar::OnScroll  
 Vom Framework aufgerufen, wenn die Outlook-Leiste einen nach oben oder unten Bildlauf.  
  
```cpp  
virtual void OnScroll(BOOL bDown);
```  
  
### <a name="parameters"></a>Parameter  
*bDown*<br/>
[in] TRUE, wenn die Outlook-Leiste wird nach unten scrollen, oder FALSE, wenn sie nach oben Scrollen wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removecustompage"></a>  CMFCOutlookBar::RemoveCustomPage  
 Entfernt eine benutzerdefinierte Registerkarte für den Outlook-Leiste.  
  
```cpp  
BOOL RemoveCustomPage(
    UINT uiPage,  
    CMFCOutlookBarTabCtrl* pTargetWnd);
```  
  
### <a name="parameters"></a>Parameter  
*uipage fehlgeschlagen*<br/>
[in] Nullbasierte Index der Seite in das übergeordnete Outlook-Fenster.  
  
*pTargetWnd*<br/>
[in] Pointerto das übergeordnete Outlook-Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Legen Sie ungleich NULL, wenn es sich bei die benutzerdefinierte Seite erfolgreich entfernt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Löschen von benutzerdefinierter Seiten. Wenn die Seite entfernt wird, wird die Steuerelement-ID an den Pool der verfügbaren IDs zurückgegeben.  
  
 Sie müssen angeben, einen Zeiger auf [CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md) Objekt, in dem die Seite derzeit entfernt befindet. Beachten Sie, dass ein Benutzer kann entfernbare Seiten zwischen verschiedenen Outlook Balken verschieben, aber die Informationen zu einer benutzerdefinierten Seite befindet sich in der Outlook-Leiste-Objekt für die Sie aufgerufen haben [CMFCOutlookBar::CreateCustomPage](#createcustompage).  
  
 Verwendung [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) um einen Zeiger auf das Outlook-Fenster zu erhalten.  
  
##  <a name="setbuttonsfont"></a>  CMFCOutlookBar::SetButtonsFont  
 Legt die Schriftart des Texts für die Schaltflächen der Outlook-Leiste fest.  
  
```cpp  
void SetButtonsFont(
    CFont* pFont,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*pFont*<br/>
[in] Gibt die neue Schriftart an.  
  
*bRedraw*<br/>
[in] Wenn TRUE, wird die Outlook-Leiste neu gezeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Schriftart für den Text auf Outlook Registerkarte Seitenschaltflächen festzulegen.  
  
##  <a name="setmode2003"></a>  CMFCOutlookBar::SetMode2003  
 Gibt an, ob das Verhalten der Outlook-Leiste, die von Outlook 2003 imitiert.  
  
```cpp  
void SetMode2003(BOOL bMode2003=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bMode2003*<br/>
[in] Bei "true", ist Office 2003-Modus aktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion aktivieren oder Deaktivieren von Office 2003-Modus. In diesem Modus hat die Outlook-Leiste eine zusätzliche Toolbar mit einer Schaltfläche "anpassen". Das Verhalten der Outlook-Leiste entspricht dem Verhalten der in Microsoft Office 2003 Outlook-Leiste.  
  
 Standardmäßig ist dieser Modus deaktiviert.  
  
> [!NOTE]
>  Diese Funktion aufgerufen werden muss, bevor [CMFCOutlookBar::Create](#create).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CBaseTabbedPane-Klasse](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane-Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md)
