---
title: Klasse CMFCOutlookBar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBar class
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
caps.latest.revision: 34
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ff58cf786e4979d64aa2b5d7ad4d1a32b96bec3d
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar-Klasse
Eine Seite im Registerformat mit dem Aussehen des **Navigationsbereichs** in Microsoft Outlook 2000 oder Outlook 2003. Die `CMFCOutlookBar` -Objekt enthält eine [CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md) Objekt und eine Reihe von Registerkarten. Die Registerkarten kann entweder [CMFCOutlookBarPane Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md) Objekte oder `CWnd`-abgeleiteten Objekten. Für den Benutzer wird die Outlook-Leiste in Form einer Reihe von Schaltflächen und eines Anzeigebereichs dargestellt. Wenn der Benutzer auf eine Schaltfläche klickt, wird der entsprechende Steuerelement- oder Schaltflächenbereich angezeigt.  
  
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
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Gibt an, ob eine leere Seite im Registerformat gelöscht werden kann. (Überschreibt [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|  
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Bestimmt, ob ein weiterer Bereich, der Outlook-Leistenbereich angedockt werden kann. (Überschreibt CDockablePane::CanAcceptPane.)|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Bestimmt, ob die Beschriftung für die Seite im Registerformat den gleichen Text als der aktiven Registerkarte angezeigt wird. (Überschreibt [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|  
|[CMFCOutlookBar::Create](#create)|Das Outlook-Leistensteuerelement wird erstellt.|  
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Erstellt eine benutzerdefinierte Registerkarte der Outlook-Leiste.|  
|`CMFCOutlookBar::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Bestimmt, ob ein Benutzer am äußeren Rand der Outlook-Leiste eine Steuerleiste angedockt werden kann.|  
|[CMFCOutlookBar::FloatTab](#floattab)|Hebt die Verankerung eines Bereichs auf, aber nur, wenn der Bereich sich auf einer lösbaren Registerkarte befindet. (Überschreibt [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Gibt die Schriftart des Texts auf den Schaltflächen der Outlook-Leiste zurück.|  
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Gibt die Größe und Position der Registerkarte Bereiche auf der Outlook-Leiste zurück. (Überschreibt [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|  
|`CMFCOutlookBar::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Bestimmt, ob das Verhalten der Outlook-Leiste der Microsoft Office Outlook 2003 ähnelt (siehe Hinweise).|  
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|Aufgerufen von [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) nach die aktive Registerkarte mit der Animation festgelegt wurde.|  
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|Aufgerufen von [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) vor einer Registerkarte Seite als die aktive Registerkarte mit der Animation festgelegt ist.|  
|[CMFCOutlookBar::OnScroll](#onscroll)|Vom Framework aufgerufen, wenn die Outlook-Leiste einen nach oben oder unten Bildlauf.|  
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Entfernt eine benutzerdefinierte Registerkarte der Outlook-Leiste.|  
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Legt die Schriftart des Texts auf den Schaltflächen der Outlook-Leiste.|  
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Gibt an, ob das Verhalten der Outlook-Leiste der in Outlook 2003 ähnelt (siehe Hinweise).|  
  
## <a name="remarks"></a>Hinweise  
 Ein Beispiel für eine Outlook-Leiste, finden Sie unter der [OutlookDemo-Beispiel: MFC-OutlookDemo-Anwendung](../../visual-cpp-samples.md).  
  
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
2.  Bei der Verarbeitung der `WM_CREATE` Nachricht in den Hauptframe Aufruf der [CMFCOutlookBar::Create](#create) Methode, um die Outlook-Leiste Registerkarten-Steuerelement zu erstellen.  
  
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
4.  Erstellen einer [CMFCOutlookBarPane Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md) -Objekt für jede Registerkarte, die Schaltflächen enthält.  
  
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
5.  Rufen Sie [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) jedes neue Registerkarte hinzufügen. Legen Sie die `bDetachable` Parameter `FALSE` auf eine Seite nicht entfernbar machen. Oder verwenden Sie [CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) entfernbare Seiten hinzufügen.  
  
 ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1,
    TRUE);

 ```  
6.  Hinzufügen einer `CWnd`-abgeleiteten Steuerelements (z. B. [CMFCShellTreeCtrl Klasse](../../mfc/reference/cmfcshelltreectrl-class.md)) als Registerkarte, erstellen Sie das Steuerelement, und rufen [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) der Outlook-Leiste hinzufügen.  
  
> [!NOTE]
>  Verwenden Sie eindeutige Steuerelement-IDs für jede [CMFCOutlookBarPane Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md) Objekt und für jeden `CWnd`-abgeleitetes Objekt.  
  
 Verwenden, um dynamisch hinzufügen oder Löschen von neuen Seiten zur Laufzeit, [CMFCOutlookBar::CreateCustomPage](#createcustompage) und [CMFCOutlookBar::RemoveCustomPage](#removecustompage).  
  
## <a name="outlook-2003-mode"></a>Outlook 2003-Modus  
 In Outlook 2003-Modus werden die Schaltflächen auf die Registerkarte am unteren Rand der Outlook-Leistenbereich positioniert. Wenn nicht genügend Platz zur Anzeige der Schaltflächen vorhanden ist, werden sie als Symbole in einem Symbolleisten-ähnliche Bereich am unteren Rand des Bereichs angezeigt.  
  
 Verwendung [CMFCOutlookBar::SetMode2003](#setmode2003) Outlook 2003-Modus aktiviert. Verwendung [CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) die Bitmap, auf die Symbole, die am unteren Rand der Outlook-Leiste angezeigt werden. Die Symbole in der Bitmap müssen Registerkartenindex angeordnet sein.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
 Gibt an, ob eine leere Seite im Registerformat gelöscht werden kann.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine leere Seite im Registerformat zerstört werden kann. andernfalls `FALSE`. Die standardmäßige Implementierung gibt immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine leere Seite im Registerformat gelöscht werden kann, wird Sie in das Framework stattdessen ausgeblendet.  
  
##  <a name="canacceptpane"></a>CMFCOutlookBar::CanAcceptPane  
 Bestimmt, ob ein weiterer Bereich, der Outlook-Leistenbereich angedockt werden kann.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf einen anderen Bereich, der in diesen Bereich angedockt werden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein weiterer Bereich kann, um die Outlook-Leistenbereich angedockt werden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Outlook-Leiste in Outlook 2003-Modus befindet, Andocken nicht unterstützt wird, sodass der Rückgabewert ist `FALSE`.  
  
 Wenn die `pBar` Parameter ist `NULL`, gibt diese Methode `FALSE`.  
  
 Diese Methode verhält sich anderenfalls als Basismethode [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane), außer dass selbst wenn die Zuordnung nicht aktiviert ist, eine Outlook-Leiste immer noch ein anderes Outlook-Leiste darüber angedockt werden aktivieren kann.  
  
##  <a name="cansetcaptiontexttotabname"></a>CMFCOutlookBar::CanSetCaptionTextToTabName  
 Bestimmt, ob die Beschriftung für die Seite im Registerformat den gleichen Text als der aktiven Registerkarte angezeigt wird.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Outlook-Leiste Fenstertitel automatisch auf den Text der aktiven Registerkarte festgelegt ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) aktivieren oder deaktivieren diese Funktion.  
  
 Im Modus für Outlook 2003 ist diese Einstellung immer aktiviert.  
  
##  <a name="create"></a>CMFCOutlookBar::Create  
 Das Outlook-Leistensteuerelement wird erstellt.  
  
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
 Gibt die Beschriftung an.  
  
 [in] `pParentWnd`  
 Gibt einen Zeiger auf ein übergeordnetes Fenster. Er darf nicht NULL sein.  
  
 [in] `rect`  
 Gibt die Outlook-Leiste Größe und Position in Pixel an.  
  
 [in] `nID`  
 Gibt die Steuerelement-ID an. Muss sich von anderen Steuerelement-IDs, die in der Anwendung verwendet werden.  
  
 [in] `dwStyle`  
 Gibt das Format des gewünschten Steuerelements angezeigt. Mögliche Werte finden Sie unter [Fensterstile](../../mfc/reference/window-styles.md).  
  
 [in] `dwControlBarStyle`  
 Gibt die Bibliothek definierten Formaten.  
  
 [in] `pContext`  
 Kontext zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CMFCOutlookBar` Objekt in zwei Schritten. Zuerst rufen Sie den Konstruktor aus, und rufen Sie dann `Create`, die das Outlook-Leistensteuerelement erstellt, und fügt es der `CMFCOutlookBar` Objekt.  
  
 Finden Sie unter [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) für die Liste der verfügbaren Bibliothek definierten Formatvorlagen durch angegeben werden `dwControlBarStyle`.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` Methode der `CMFCOutlookBar` Klasse. Dieser Codeausschnitt ist Teil der [Outlook mit mehreren Ansichten Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews&#1;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews&#2;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]  
  
##  <a name="createcustompage"></a>CMFCOutlookBar::CreateCustomPage  
 Erstellt eine benutzerdefinierte Registerkarte der Outlook-Leiste.  
  
```  
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,  
    BOOL bActivatePage=TRUE,  
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,  
    BOOL bEnableTextLabels=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszPageName`  
 Die Seite Bezeichnung.  
  
 [in] `bActivatePage`  
 Wenn `TRUE`, die Seite wird bei der Erstellung aktiviert.  
  
 [in] `dwEnabledDocking`  
 Eine Kombination von CBRS_ALIGN_-Flags, die angibt, die aktivierte Andocken Seiten, wenn die Seite getrennt wird.  
  
 [in] `bEnableTextLabels`  
 Wenn `TRUE`, die Beschriftungen für die Schaltflächen, die sich auf der Seite aktiviert sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Seite oder `NULL` Wenn Fehler bei der Erstellung.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Benutzer zum Erstellen benutzerdefinierter Outlook-Leiste Seiten zu aktivieren. Sie können bis zu 100 Seiten pro Anwendung erstellen. Das Seitensteuerelement starten IDs von 0xF000. Die Erstellung schlägt fehl, wenn die Gesamtzahl der Seiten, die benutzerdefinierten Outlook-Leiste 100 überschreitet.  
  
 Verwendung [CMFCOutlookBar::RemoveCustomPage](#removecustompage) So löschen Sie benutzerdefinierte Seiten.  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCOutlookBar::DoesAllowDynInsertBefore  
 Gibt an, ob ein Benutzer einen Bereich am äußeren Rand der Outlook-Leiste angedockt werden kann.  
  
```  
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework Ruft die `DoesAllowDynInsertBefore` Methode bei der Suche nach einem Speicherort zu einen dynamischen Bereich anzudocken. Wenn die Funktion zurückgibt `FALSE`, das Framework lässt nicht die Dockingstation alle dynamischen Bereich an den äußeren Kanten des Bereichs.  
  
 Normalerweise erstellen Sie eine Outlook-Leiste als ein statisches Steuerelement verankerte. Sie können diese Funktion in einer abgeleiteten Klasse überschreiben und `TRUE` dieses Verhalten zu ändern.  
  
> [!NOTE]
>  Da dynamische Bereiche den Status des angedockten statische Bereiche angedockt überprüfen, sollten Sie nach statischen Bereiche möglichst dynamische Bereiche andocken.  
  
##  <a name="floattab"></a>CMFCOutlookBar::FloatTab  
 Befindet sich einen Bereich.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf den Bereich in einen Gleitkommawert.  
  
 [in] `nTabID`  
 Der nullbasierte Index der Registerkarte in float-Wert.  
  
 [in] `dockMethod`  
 Gibt die Methode zu verwenden, um den Bereich loszulösen.  Weitere Informationen finden Sie unter [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).  
  
 [in] `bHide`  
 `TRUE`um das Fenster auszublenden vor Gleitkommawert; andernfalls `FALSE`. Anders als die Basisklassenversion dieser Methode dieser Parameter keinen Standardwert aufweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich umfließt; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist mit [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) außer dass es nicht die letzte verbleibende Registerkarte auf eine Outlook-Leistensteuerelement float aktiviert wird.  
  
##  <a name="getbuttonsfont"></a>CMFCOutlookBar::GetButtonsFont  
 Gibt die Schriftart des Texts auf der Seite Schaltfläche Registerkarten der Outlook-Leiste zurück.  
  
```  
CFont* GetButtonsFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Font-Objekt, das zum Anzeigen von Text in Outlook Balken Seitenregister Schaltfläche verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Schriftart abzurufen, die verwendet wird, um den Text auf Outlook-Schaltfläche Registerkarten anzuzeigen. Sie können die Schriftart festlegen, durch Aufrufen von für [CMFCOutlookBar::SetButtonsFont](#setbuttonsfont).  
  
##  <a name="gettabarea"></a>CMFCOutlookBar::GetTabArea  
 Bestimmt die Größe und Position der Registerkarte Bereiche auf der Outlook-Leiste.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectTabAreaTop`  
 Enthält die Größe und Position des oberen Registerkartenbereichs (in Clientkoordinaten), wenn die Funktion zurückgibt.  
  
 [out] `rectTabAreaBottom`  
 Enthält die Größe und Position des Registerkartenbereichs unten (in Clientkoordinaten), wenn die Funktion zurückgibt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um das Andocken an die Zielbereich zu bestimmen. Das Framework fest, dass der Benutzer den Bereich auf der Ziel im Registerkartenbereich angedockt werden zieht, versucht es den ersten Bereich als neue Registerkarte im Ziel-Bereich hinzufügen. Andernfalls wird versucht, den ersten Bereich an eine entsprechende Seite des Bereichs Ziel anzudocken. Das Framework erstellt einen neuen Container mit einem Schieberegler, um zusätzliche angedockten Bereich gerecht zu werden.  
  
 Die standardmäßige Implementierung der `GetTabArea` gibt den gesamten Clientbereich der Outlook-Leiste, wenn die Outlook-Leiste statische; ist, ist, wenn die Outlook-Leiste float nicht möglich. Andernfalls wird den Bereich, den Schaltflächen am oberen und unteren Rand der Outlook-Leistensteuerelement nutzen.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse `CMFCOutlookBar` dieses Verhalten zu ändern.  
  
##  <a name="ismode2003"></a>CMFCOutlookBar::IsMode2003  
 Gibt an, ob das Verhalten der Outlook-Leiste, die von Microsoft Office Outlook 2003 imitiert.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Outlook-Leiste in Microsoft Office 2003-Modus ausgeführt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diesen Modus aktivieren, mit [CMFCOutlookBar::SetMode2003](#setmode2003).  
  
##  <a name="onafteranimation"></a>CMFCOutlookBar::OnAfterAnimation  
 Aufgerufen von [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) nach die aktive Registerkarte mit der Animation festgelegt wurde.  
  
```  
virtual void OnAfterAnimation(int nPage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nPage`  
 Der nullbasierte Index der Registerkarte, die aktive vorgenommen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Der visuelle Effekt der aktive Registerkarte festlegen, hängt davon ab, ob Sie die Animation aktiviert haben. Weitere Informationen finden Sie unter [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).  
  
##  <a name="onbeforeanimation"></a>CMFCOutlookBar::OnBeforeAnimation  
 Aufgerufen von [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) vor einer Registerkarte Seite als die aktive Registerkarte mit der Animation festgelegt ist.  
  
```  
virtual BOOL OnBeforeAnimation(int nPage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nPage`  
 Der nullbasierte Index der Registerkarte, die aktiviert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn Animation verwendet werden soll, bei der Festlegung der neuen aktiven Registerkarte oder `FALSE` Animation deaktiviert werden sollten.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onscroll"></a>CMFCOutlookBar::OnScroll  
 Vom Framework aufgerufen, wenn die Outlook-Leiste einen nach oben oder unten Bildlauf.  
  
```  
virtual void OnScroll(BOOL bDown);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDown`  
 `TRUE`Wenn die Outlook-Leiste einen Bildlauf nach unten ausführt oder `FALSE` , wenn es um Bildlauf ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removecustompage"></a>CMFCOutlookBar::RemoveCustomPage  
 Entfernt eine benutzerdefinierte Registerkarte der Outlook-Leiste.  
  
```  
BOOL RemoveCustomPage(
    UINT uiPage,  
    CMFCOutlookBarTabCtrl* pTargetWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiPage`  
 Nullbasierte Index der Seite in der übergeordneten Outlook-Fenster.  
  
 [in] `pTargetWnd`  
 Pointerto das übergeordnete Outlook-Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die benutzerdefinierte Seite erfolgreich entfernt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um benutzerdefinierte Seiten zu löschen. Wenn die Seite entfernt wird die Steuerelement-ID an den Pool der verfügbaren IDs zurückgegeben.  
  
 Geben Sie einen Zeiger auf [CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md) Objekt, in dem die Seite derzeit entfernt werden befindet. Beachten Sie, dass ein Benutzer kann zwischen verschiedenen Outlook Balken entfernbare Seiten verschieben, aber die Informationen über eine benutzerdefinierte Seite befindet sich in der Outlook-Leiste-Objekt für die Sie aufgerufen haben [CMFCOutlookBar::CreateCustomPage](#createcustompage).  
  
 Verwendung [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) um einen Zeiger auf das Outlook-Fenster zu erhalten.  
  
##  <a name="setbuttonsfont"></a>CMFCOutlookBar::SetButtonsFont  
 Legt die Schriftart des Texts auf den Schaltflächen der Outlook-Leiste.  
  
```  
void SetButtonsFont(
    CFont* pFont,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFont`  
 Gibt die neue Schriftart.  
  
 [in] `bRedraw`  
 Wenn `TRUE`, wird die Outlook-Leiste neu gezeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode eine Schriftart für den Text in Outlook Registerkartenschaltflächen festlegen.  
  
##  <a name="setmode2003"></a>CMFCOutlookBar::SetMode2003  
 Gibt an, ob das Verhalten der Outlook-Leiste, die von Outlook 2003 imitiert.  
  
```  
void SetMode2003(BOOL bMode2003=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMode2003`  
 Wenn TRUE, ist Office 2003-Modus aktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion aktivieren oder Deaktivieren von Office 2003-Modus. In diesem Modus hat die Outlook-Leiste eine zusätzliche Symbolleiste mit der Anpassungsschaltfläche. Das Verhalten der Outlook-Leiste entspricht das Verhalten der Outlook-Leiste in Microsoft Office 2003.  
  
 Standardmäßig ist dieser Modus deaktiviert.  
  
> [!NOTE]
>  Diese Funktion muss aufgerufen werden, bevor [CMFCOutlookBar::Create](#create).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CBaseTabbedPane-Klasse](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane-Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md)

