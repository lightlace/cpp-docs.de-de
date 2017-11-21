---
title: CMFCOutlookBar-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 00988ef4a0b70561ec3a5687502ddae95508dad5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar-Klasse
Eine Seite im Registerformat mit dem Aussehen des **Navigationsbereichs** in Microsoft Outlook 2000 oder Outlook 2003. Die `CMFCOutlookBar` Objekt enthält eine [CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md) Objekt und eine Reihe von Registerkarten. Die Registerkarten können es sich um [CMFCOutlookBarPane Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md) Objekte oder `CWnd`--abgeleitete Objekte. Für den Benutzer wird die Outlook-Leiste in Form einer Reihe von Schaltflächen und eines Anzeigebereichs dargestellt. Wenn der Benutzer auf eine Schaltfläche klickt, wird der entsprechende Steuerelement- oder Schaltflächenbereich angezeigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCOutlookBar::CMFCOutlookBar`|Standardkonstruktor|  
|`CMFCOutlookBar::~CMFCOutlookBar`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Gibt an, ob es sich bei einem leeren Bereich im Registerkartenformat gelöscht werden kann. (Überschreibt [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|  
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Bestimmt, ob es sich bei einem anderen Bereich an die Outlook-Leistenbereich angedockt werden kann. (Überschreibt CDockablePane::CanAcceptPane.)|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Bestimmt, ob die Beschriftung für den Bereich im Registerkartenformat als aktive Registerkarte zeigt den gleichen Text an. (Überschreibt [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|  
|[CMFCOutlookBar::Create](#create)|Erstellt das Outlook-Steuerelement.|  
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Erstellt eine benutzerdefinierte Registerkarte des Outlook-Leiste.|  
|`CMFCOutlookBar::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Bestimmt, ob ein Benutzer eine Steuerleiste am äußeren Rand der Outlook-Leiste Andocken kann.|  
|[CMFCOutlookBar::FloatTab](#floattab)|Hebt die Verankerung eines Bereichs auf, aber nur, wenn der Bereich sich auf einer lösbaren Registerkarte befindet. (Überschreibt [cbasetabbedpane:: Floattab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Gibt die Schriftart des Texts auf die Schaltflächen der Outlook-Leiste zurück.|  
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Gibt die Größe und Position der Registerkarte Bereiche der Outlook-Leiste zurück. (Überschreibt [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|  
|`CMFCOutlookBar::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Bestimmt, ob das Verhalten von der Outlook-Leiste imitiert, die von Microsoft Office Outlook 2003 (siehe "Hinweise").|  
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|Wird aufgerufen, indem [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) nachdem die aktive Registerkarte mit Animation festgelegt wurde.|  
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|Wird aufgerufen, indem [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) Seite vor einer Registerkarte als aktive Registerkarte mit Animation festgelegt ist.|  
|[CMFCOutlookBar::OnScroll](#onscroll)|Vom Framework aufgerufen, wenn die Outlook-Leiste einen nach oben oder unten Bildlauf.|  
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Entfernt eine benutzerdefinierte Registerkarte des Outlook-Leiste.|  
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Legt die Schriftart des Texts auf die Schaltflächen der Outlook-Leiste.|  
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Gibt an, ob das Verhalten von der Outlook-Leiste imitiert, die von Outlook 2003 (siehe "Hinweise").|  
  
## <a name="remarks"></a>Hinweise  
 Ein Beispiel für eine Outlook-Leiste, finden Sie unter der [OutlookDemo-Beispiel: MFC-OutlookDemo Anwendung](../../visual-cpp-samples.md).  
  
## <a name="implementing-the-outlook-bar"></a>Implementieren der Outlook-Leiste  
 Befolgen Sie folgende Schritte, um das `CMFCOutlookBar`-Steuerelement in Ihrer Anwendung zu verwenden:  
  
1.  Betten Sie ein `CMFCOutlookBar`-Objekt in die Hauptframe-Fensterklasse ein.  
  
 ```  
    class CMainFrame : public CMDIFrameWnd  
 { ...  
    CMFCOutlookBar m_wndOutlookBar;  
    CMFCOutlookBarPane m_wndOutlookPane;  
 ... };  
 ```  
2.  Bei der Verarbeitung der `WM_CREATE` Nachricht in die Hauptframe Aufruf der [CMFCOutlookBar::Create](#create) Methode, um die Outlook-Leiste Registerkarten-Steuerelement zu erstellen.  
  
 ```  
    m_wndOutlookBar.Create (_T("Shortcuts"),
    this,
    CRect (0,
    0,
    100,
    100),
    ID_VIEW_OUTLOOKBAR,
    WS_CHILD | WS_VISIBLE | CBRS_LEFT);

 ```  
3.  Rufen Sie einen Zeiger auf die zugrunde liegende `CMFCOutlookBarTabCtrl` mit [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow).  
  
 ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();

 ```  
4.  Erstellen einer [CMFCOutlookBarPane Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md) Objekt für jede Registerkarte, die Schaltflächen enthält.  
  
 ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar,
    AFX_DEFAULT_TOOLBAR_STYLE,
    ID_OUTLOOK_PANE_GENERAL,
    AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);
*// make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);
*// add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About",
    ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open",
    ID_FILE_OPEN);

 ```  
5.  Rufen Sie [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) jede neue Registerkarte hinzufügen. Legen Sie die `bDetachable` Parameter `FALSE` auf eine Seite nicht lösbare stellen. Oder verwenden Sie [CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) lösbare Seiten hinzufügen.  
  
 ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1,
    TRUE);

 ```  
6.  Hinzufügen einer `CWnd`-abgeleiteten Steuerelements (z. B. [CMFCShellTreeCtrl Klasse](../../mfc/reference/cmfcshelltreectrl-class.md)) als eine Registerkarte zu erstellen, das Steuerelement, und rufen [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) der Outlook-Leiste hinzuzufügen.  
  
> [!NOTE]
>  Sie sollten eindeutige Steuerelement-IDs verwenden, für die einzelnen [CMFCOutlookBarPane Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md) Objekt und für jede `CWnd`-abgeleitetes Objekt.  
  
 Um dynamisch hinzuzufügen, oder neue Seiten zur Laufzeit zu löschen, verwenden Sie [CMFCOutlookBar::CreateCustomPage](#createcustompage) und [CMFCOutlookBar::RemoveCustomPage](#removecustompage).  
  
## <a name="outlook-2003-mode"></a>Outlook 2003-Modus  
 In Outlook 2003-Modus werden die Schaltflächen auf die Registerkarte am unteren Rand der Outlook-Leistenbereich positioniert. Wenn nicht ausreichend Platz zur Anzeige der Schaltflächen vorhanden ist, werden sie als Symbole in einem Bereich symbolleistenähnlicher entlang des unteren Bereich angezeigt.  
  
 Verwendung [CMFCOutlookBar::SetMode2003](#setmode2003) Outlook 2003-Modus zu aktivieren. Verwendung [CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) Bitmap festlegen, die die Symbole enthält, die am unteren Rand der Outlook-Leiste angezeigt werden. Die Symbole in der Bitmap müssen Registerkartenindex geordnet werden.  
  
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
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCOutlookBar::AllowDestroyEmptyTabbedPane  
 Gibt an, ob es sich bei einem leeren Bereich im Registerkartenformat gelöscht werden kann.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie einen leeren Bereich im Registerkartenformat zerstört werden kann. andernfalls `FALSE`. Gibt die standardmäßige Implementierung immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen leeren Bereich im Registerkartenformat kann nicht gelöscht werden, das Framework stattdessen ausgeblendet.  
  
##  <a name="canacceptpane"></a>CMFCOutlookBar::CanAcceptPane  
 Bestimmt, ob es sich bei einem anderen Bereich an die Outlook-Leistenbereich angedockt werden kann.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf einen anderen Bereich an, der in diesen Bereich angedockt werden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie einen anderen Bereich angedockt werden kann, um die Outlook-Leistenbereich; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Outlook-Leiste in Outlook 2003-Modus befindet, Andocken wird nicht unterstützt, sodass der Rückgabewert ist `FALSE`.  
  
 Wenn die `pBar` Parameter ist `NULL`, gibt diese Methode `FALSE`.  
  
 Diese Methode verhält sich hingegen als der Basismethode [cbasepane:: Canacceptpane](../../mfc/reference/cbasepane-class.md#canacceptpane), außer dass selbst wenn Andocken nicht aktiviert ist, eine Outlook-Leiste noch einem anderen Outlook-Leiste darüber angedockt werden aktivieren kann.  
  
##  <a name="cansetcaptiontexttotabname"></a>CMFCOutlookBar::CanSetCaptionTextToTabName  
 Bestimmt, ob die Beschriftung für den Bereich im Registerkartenformat als aktive Registerkarte zeigt den gleichen Text an.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Outlook-Leiste fensterbeschriftung automatisch auf den Text der aktiven Registerkarte festgelegt wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) aktivieren oder deaktivieren diese Funktionalität.  
  
 Diese Einstellung ist im Outlook 2003-Modus immer aktiviert.  
  
##  <a name="create"></a>CMFCOutlookBar::Create  
 Erstellt das Outlook-Steuerelement.  
  
```  
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
 [in] `lpszCaption`  
 Gibt die fensterbeschriftung.  
  
 [in] `pParentWnd`  
 Gibt einen Zeiger auf ein übergeordnetes Fenster. Es darf nicht NULL sein.  
  
 [in] `rect`  
 Gibt an, die Outlook-Leiste Größe und Position in Pixel.  
  
 [in] `nID`  
 Gibt an, die Steuerelement-ID. Muss sich von anderen Steuerelement-IDs, die in der Anwendung verwendet werden.  
  
 [in] `dwStyle`  
 Gibt das Format des gewünschten Steuerelements Balken an. Mögliche Werte finden Sie unter [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `dwControlBarStyle`  
 Gibt an, die spezielle Bibliothek definierte Stile.  
  
 [in] `pContext`  
 Kontext zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CMFCOutlookBar` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor aus, und rufen dann `Create`, der das Outlook-Steuerelement erstellt, und fügt es der `CMFCOutlookBar` Objekt.  
  
 Finden Sie unter [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex) für die Liste der verfügbaren Bibliothek definierte Formatvorlagen durch angegeben werden `dwControlBarStyle`.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` Methode der `CMFCOutlookBar` Klasse. Dieser Codeausschnitt ist Teil der [Outlook mehreren Ansichten Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]  
  
##  <a name="createcustompage"></a>CMFCOutlookBar::CreateCustomPage  
 Erstellt eine benutzerdefinierte Registerkarte des Outlook-Leiste.  
  
```  
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,  
    BOOL bActivatePage=TRUE,  
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,  
    BOOL bEnableTextLabels=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszPageName`  
 Die Seite-Bezeichnung.  
  
 [in] `bActivatePage`  
 Wenn `TRUE`, die Seite wird bei der Erstellung aktiviert.  
  
 [in] `dwEnabledDocking`  
 Eine Kombination von CBRS_ALIGN_-Flags, die angibt, die aktiviert Andocken Seiten aus, wenn die Seite getrennt wird.  
  
 [in] `bEnableTextLabels`  
 Wenn `TRUE`, die Bezeichnungen aktiviert sind, für die Schaltflächen, die auf der Seite befinden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Seite oder `NULL` Wenn Fehler beim Erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um den Benutzern das Erstellen von benutzerdefinierter Outlook-Leiste Seiten zu aktivieren. Sie können bis zu 100 Seiten pro Anwendung erstellen. Das Seitensteuerelement starten IDs über "0xf000". Die Erstellung schlägt fehl, wenn die Gesamtanzahl der Seiten, die benutzerdefinierte Outlook-Leiste 100 überschreitet.  
  
 Verwendung [CMFCOutlookBar::RemoveCustomPage](#removecustompage) So löschen Sie benutzerdefinierte Seiten.  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCOutlookBar::DoesAllowDynInsertBefore  
 Gibt an, ob ein Benutzer einen Bereich am äußeren Rand der Outlook-Leiste Andocken kann.  
  
```  
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework Ruft die `DoesAllowDynInsertBefore` Methode, wenn er nach einem Speicherort sucht zu einen dynamischen Bereich anzudocken. Wenn die Funktion zurückgibt `FALSE`, das Framework lässt sich nicht darauf aus, das Andocken alle dynamischen Bereich in den äußeren Rändern des Bereichs.  
  
 In der Regel erstellen Sie eine Outlook-Leiste als statische unverankerte-Steuerelement. Sie können diese Funktion in einer abgeleiteten Klasse überschreiben und `TRUE` dieses Verhalten zu ändern.  
  
> [!NOTE]
>  Da dynamische Bereiche des Status der angedockten statische Bereiche beim Andocken überprüfen sollten Sie nach dem statischen Bereiche nach Möglichkeit dynamische Bereiche andocken.  
  
##  <a name="floattab"></a>CMFCOutlookBar::FloatTab  
 Wird einen Bereich verschoben.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf den Bereich, um "float".  
  
 [in] `nTabID`  
 Der nullbasierte Index der Registerkarte "float".  
  
 [in] `dockMethod`  
 Gibt die Methode zu verwenden, um den Bereich "float" auszuführen.  Weitere Informationen finden Sie unter [cbasetabbedpane:: Floattab](../../mfc/reference/cbasetabbedpane-class.md#floattab).  
  
 [in] `bHide`  
 `TRUE`der Bereich ausgeblendet vor Gleitkommawert; andernfalls `FALSE`. Anders als die Basisklassenversion dieser Methode ist dieser Parameter keinen Standardwert aufweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich umfließt; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entspricht [cbasetabbedpane:: Floattab](../../mfc/reference/cbasetabbedpane-class.md#floattab) mit dem Unterschied, dass es nicht die letzte verbleibende Registerkarte auf ein Outlook-Leiste-Steuerelement, "float" aktiviert.  
  
##  <a name="getbuttonsfont"></a>CMFCOutlookBar::GetButtonsFont  
 Gibt die Schriftart des Texts auf der Seite "-Schaltfläche Registerkarten der Outlook-Leiste zurück.  
  
```  
CFont* GetButtonsFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Font-Objekt, das zum Anzeigen von Text in Outlook Strich Schaltfläche Seitenregister verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Schriftart abzurufen, die verwendet wird, um den Text auf Outlook Schaltfläche Seitenregister anzuzeigen. Sie können die Schriftart festlegen, durch den Aufruf auf [CMFCOutlookBar::SetButtonsFont](#setbuttonsfont).  
  
##  <a name="gettabarea"></a>CMFCOutlookBar::GetTabArea  
 Bestimmt die Größe und Position der Bereiche Registerkarte auf der Outlook-Leiste.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectTabAreaTop`  
 Enthält die Größe und Position des Registerkartenbereichs Top (in Clientkoordinaten), wenn die Funktion zurückgibt.  
  
 [out] `rectTabAreaBottom`  
 Enthält die Größe und Position des Registerkartenbereichs unteren (in Clientkoordinaten), wenn die Funktion zurückgibt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um den Typ des Andocken an die Zielbereich zu bestimmen. Wenn das Framework feststellt, dass der Benutzer den Bereich, um über die Ziel im Registerkartenbereich angedockt werden zieht, wird versucht, den ersten Bereich als neue Registerkarte des Bereichs "Ziel" hinzufügen. Andernfalls wird versucht, den ersten Bereich auf einen entsprechenden Rand des Bereichs Ziel anzudocken. Das Framework erstellt einen neuen Container mit einem Schieberegler, um den zusätzlichen angedockten Bereich Rechnung zu tragen.  
  
 Die standardmäßige Implementierung des `GetTabArea` gibt den gesamten Clientbereich der Outlook-Leiste zurück, wenn die Outlook-Leiste statische; ist, ist, wenn die Outlook-Leiste float nicht möglich. Andernfalls wird den Bereich, den Schaltflächen am oberen und unteren Rand des Steuerelements des Outlook-Leiste zu akzeptieren zurückgegeben.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse `CMFCOutlookBar` dieses Verhalten zu ändern.  
  
##  <a name="ismode2003"></a>CMFCOutlookBar::IsMode2003  
 Gibt an, ob das Verhalten von der Outlook-Leiste, die von Microsoft Office Outlook 2003 imitiert.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Outlook-Leiste in Microsoft Office 2003-Modus ausgeführt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diesen Modus aktivieren, mit [CMFCOutlookBar::SetMode2003](#setmode2003).  
  
##  <a name="onafteranimation"></a>CMFCOutlookBar::OnAfterAnimation  
 Wird aufgerufen, indem [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) nachdem die aktive Registerkarte mit Animation festgelegt wurde.  
  
```  
virtual void OnAfterAnimation(int nPage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nPage`  
 Der nullbasierte Index der Registerkarte, die aktive vorgenommen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die visuelle Auswirkung der Einstellung der aktiven Registerkarte hängt davon ab, ob Sie die Animation aktiviert haben. Weitere Informationen finden Sie unter [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).  
  
##  <a name="onbeforeanimation"></a>CMFCOutlookBar::OnBeforeAnimation  
 Wird aufgerufen, indem [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) Seite vor einer Registerkarte als aktive Registerkarte mit Animation festgelegt ist.  
  
```  
virtual BOOL OnBeforeAnimation(int nPage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nPage`  
 Der nullbasierte Index der Registerkarte, die aktiv festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn Animation verwendet werden soll, bei der Festlegung der neuen aktiven Registerkarte oder `FALSE` Wenn Animation deaktiviert werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onscroll"></a>CMFCOutlookBar::OnScroll  
 Vom Framework aufgerufen, wenn die Outlook-Leiste einen nach oben oder unten Bildlauf.  
  
```  
virtual void OnScroll(BOOL bDown);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDown`  
 `TRUE`Wenn die Outlook-Leiste, Durchführen eines Bildlaufs ist oder `FALSE` Wenn oben durchführen eines Bildlaufs ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removecustompage"></a>CMFCOutlookBar::RemoveCustomPage  
 Entfernt eine benutzerdefinierte Registerkartenseite für die Outlook-Leiste.  
  
```  
BOOL RemoveCustomPage(
    UINT uiPage,  
    CMFCOutlookBarTabCtrl* pTargetWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiPage`  
 Nullbasierte Index der Seite in der übergeordneten Outlook-Fenster.  
  
 [in] `pTargetWnd`  
 Pointerto Outlook übergeordneten Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die benutzerdefinierte Seite erfolgreich entfernt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Löschen benutzerdefinierter Seiten. Wenn die Seite entfernt wird, wird die Steuerelement-ID an den Pool der verfügbaren IDs zurückgegeben.  
  
 Sie müssen angeben, einen Zeiger auf [CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md) Objekt, in dem die Seite derzeit entfernt werden befindet. Beachten Sie, dass ein Benutzer kann lösbare Seiten zwischen verschiedenen Outlook Balken verschieben, aber die Informationen über eine benutzerdefinierte Seite befindet sich in der Outlook-Leiste-Objekt für das Sie aufgerufen haben [CMFCOutlookBar::CreateCustomPage](#createcustompage).  
  
 Verwendung [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) um einen Zeiger auf das Outlook-Fenster zu erhalten.  
  
##  <a name="setbuttonsfont"></a>CMFCOutlookBar::SetButtonsFont  
 Legt die Schriftart des Texts auf die Schaltflächen der Outlook-Leiste.  
  
```  
void SetButtonsFont(
    CFont* pFont,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFont`  
 Gibt die neue Schriftart an.  
  
 [in] `bRedraw`  
 Wenn `TRUE`, wird die Outlook-Leiste neu gezeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Schriftart für den auf Schaltflächen Outlook Registerkarte angezeigten Text festzulegen.  
  
##  <a name="setmode2003"></a>CMFCOutlookBar::SetMode2003  
 Gibt an, ob das Verhalten von der Outlook-Leiste, die von Outlook 2003 imitiert.  
  
```  
void SetMode2003(BOOL bMode2003=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMode2003`  
 Bei "true", ist Office 2003-Modus aktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion aktivieren oder Deaktivieren von Office 2003-Modus. In diesem Modus hat die Outlook-Leiste eine zusätzliche Symbolleiste mit einer Schaltfläche "Anpassung". Das Verhalten von der Outlook-Leiste entspricht das Verhalten von der Outlook-Leiste in Microsoft Office 2003.  
  
 Standardmäßig ist dieser Modus deaktiviert.  
  
> [!NOTE]
>  Diese Funktion aufgerufen werden muss, bevor [CMFCOutlookBar::Create](#create).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CBaseTabbedPane-Klasse](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane-Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md)
