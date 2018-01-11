---
title: CMDIChildWndEx-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx::ActivateTopLevelFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AdjustDockingLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnMDITabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnTaskBarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnWindowsList
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPaneLeftOf
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableAutoHidePanes
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableDocking
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDockingManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDocumentName
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameIcon
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameText
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabProxyWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarPreviewWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetToolbarButtonToolTipText
- AFXMDICHILDWNDEX/CMDIChildWndEx::InsertPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::InvalidateIconicBitmaps
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsPointNearDockSite
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsReadOnly
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsRegisteredWithTaskbarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarTabsSupportEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicLivePreviewBitmap
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicThumbnail
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnMoveMiniFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnSetPreviewMode
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailStretch
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnUpdateFrameTitle
- AFXMDICHILDWNDEX/CMDIChildWndEx::PaneFromPoint
- AFXMDICHILDWNDEX/CMDIChildWndEx::RecalcLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::RegisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::RemovePaneFromDockManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabActive
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabOrder
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabProperties
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::ShowPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::UnregisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::UpdateTaskbarTabIcon
dev_langs: C++
helpviewer_keywords:
- CMDIChildWndEx [MFC], ActivateTopLevelFrame
- CMDIChildWndEx [MFC], AddPane
- CMDIChildWndEx [MFC], AddTabbedPane
- CMDIChildWndEx [MFC], AdjustDockingLayout
- CMDIChildWndEx [MFC], CanShowOnMDITabs
- CMDIChildWndEx [MFC], CanShowOnTaskBarTabs
- CMDIChildWndEx [MFC], CanShowOnWindowsList
- CMDIChildWndEx [MFC], DockPane
- CMDIChildWndEx [MFC], DockPaneLeftOf
- CMDIChildWndEx [MFC], EnableAutoHidePanes
- CMDIChildWndEx [MFC], EnableDocking
- CMDIChildWndEx [MFC], EnableTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetDockingManager
- CMDIChildWndEx [MFC], GetDocumentName
- CMDIChildWndEx [MFC], GetFrameIcon
- CMDIChildWndEx [MFC], GetFrameText
- CMDIChildWndEx [MFC], GetPane
- CMDIChildWndEx [MFC], GetRelatedTabGroup
- CMDIChildWndEx [MFC], GetTabbedPane
- CMDIChildWndEx [MFC], GetTabProxyWnd
- CMDIChildWndEx [MFC], GetTaskbarPreviewWnd
- CMDIChildWndEx [MFC], GetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetToolbarButtonToolTipText
- CMDIChildWndEx [MFC], InsertPane
- CMDIChildWndEx [MFC], InvalidateIconicBitmaps
- CMDIChildWndEx [MFC], IsPointNearDockSite
- CMDIChildWndEx [MFC], IsReadOnly
- CMDIChildWndEx [MFC], IsRegisteredWithTaskbarTabs
- CMDIChildWndEx [MFC], IsTabbedPane
- CMDIChildWndEx [MFC], IsTaskbarTabsSupportEnabled
- CMDIChildWndEx [MFC], IsTaskbarThumbnailClipRectEnabled
- CMDIChildWndEx [MFC], m_dwDefaultTaskbarTabPropertyFlags
- CMDIChildWndEx [MFC], OnGetIconicLivePreviewBitmap
- CMDIChildWndEx [MFC], OnGetIconicThumbnail
- CMDIChildWndEx [MFC], OnMoveMiniFrame
- CMDIChildWndEx [MFC], OnPressTaskbarThmbnailCloseButton
- CMDIChildWndEx [MFC], OnSetPreviewMode
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailMouseActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailStretch
- CMDIChildWndEx [MFC], OnUpdateFrameTitle
- CMDIChildWndEx [MFC], PaneFromPoint
- CMDIChildWndEx [MFC], RecalcLayout
- CMDIChildWndEx [MFC], RegisterTaskbarTab
- CMDIChildWndEx [MFC], RemovePaneFromDockManager
- CMDIChildWndEx [MFC], SetRelatedTabGroup
- CMDIChildWndEx [MFC], SetTaskbarTabActive
- CMDIChildWndEx [MFC], SetTaskbarTabOrder
- CMDIChildWndEx [MFC], SetTaskbarTabProperties
- CMDIChildWndEx [MFC], SetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], ShowPane
- CMDIChildWndEx [MFC], UnregisterTaskbarTab
- CMDIChildWndEx [MFC], UpdateTaskbarTabIcon
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
caps.latest.revision: "35"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 21b302c14d2b4aa17b2818e489a1400230332521
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmdichildwndex-class"></a>CMDIChildWndEx-Klasse
Die `CMDIChildWndEx` Klasse stellt die Funktionalität eines Windows untergeordneten Fensters der multiple Document Interface (MDI) bereit. Erweitert die Funktionalität des [CMDIChildWnd-Klasse](../../mfc/reference/cmdichildwnd-class.md). Das Framework benötigt diese Klasse, wenn eine MDI-Anwendung bestimmte MFC-Klassen verwendet.  
 
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  

  
## <a name="syntax"></a>Syntax  
  
```  
class CMDIChildWndEx : public CMDIChildWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDIChildWndEx::ActivateTopLevelFrame](#activatetoplevelframe)|Intern vom Framework aufgerufen, um die obersten Ebenen Rahmen zu aktivieren, wenn die Anwendung über eine Registerkarte Taskleiste aktiviert werden soll.|  
|`CMDIChildWndEx::AddDockSite`|Diese Methode ist weder verwendet noch implementiert.|  
|[CMDIChildWndEx::AddPane](#addpane)|Fügt einen Bereich hinzu.|  
|[CMDIChildWndEx::AddTabbedPane](#addtabbedpane)|Fügt einen Bereich im Registerkartenformat hinzu.|  
|[CMDIChildWndEx::AdjustDockingLayout](#adjustdockinglayout)|Passt die am Layout des Docks an.|  
|[CMDIChildWndEx::CanShowOnMDITabs](#canshowonmditabs)||  
|[CMDIChildWndEx::CanShowOnTaskBarTabs](#canshowontaskbartabs)|Das Framework angewiesen wird, ob diese untergeordneten MDI-Fensters auf Windows 7-Taskleiste Registerkarten angezeigt werden kann.|  
|[CMDIChildWndEx::CanShowOnWindowsList](#canshowonwindowslist)|Gibt `TRUE` , wenn der Name der MDI-untergeordneten Fenster kann, in angezeigt werden der [CMFCWindowsManagerDialog Klasse](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) (Dialogfeld). Andernfalls wird `FALSE` zurückgegeben.|  
|`CMDIChildWndEx::CreateObject`|Wird aufgerufen, durch das Framework eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMDIChildWndEx::DockPane](#dockpane)|Dockt einen Bereich an.|  
|[CMDIChildWndEx::DockPaneLeftOf](#dockpaneleftof)|Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.|  
|[CMDIChildWndEx::EnableAutoHidePanes](#enableautohidepanes)|Ermöglicht das automatischen Ausblendemodus für Bereiche, wenn sie sich an den angegebenen Seiten des Fensters angedockt sind.|  
|[CMDIChildWndEx::EnableDocking](#enabledocking)|Ermöglicht das Andocken von untergeordneten Fensters zum Hauptframe.|  
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](#enabletaskbarthumbnailcliprect)|Aktiviert oder deaktiviert die automatische Auswahl von einem Teil des Clientbereichs des Fensters, als dieses Fensters Miniaturansicht in der Taskleiste angezeigt.|  
|[CMDIChildWndEx::GetDockingManager](#getdockingmanager)||  
|[CMDIChildWndEx::GetDocumentName](#getdocumentname)|Gibt den Namen des Dokuments, das in der untergeordneten MDI-Fensters angezeigt wird.|  
|[CMDIChildWndEx::GetFrameIcon](#getframeicon)|Wird aufgerufen, durch das Framework zum Abrufen von untergeordneten MDI-Symbols.|  
|[CMDIChildWndEx::GetFrameText](#getframetext)|Wird aufgerufen, durch das Framework zum Abrufen des Texts für die untergeordneten MDI-Fensters.|  
|[CMDIChildWndEx::GetPane](#getpane)|Sucht nach einem Bereich durch das angegebene Steuerelement-ID.|  
|[CMDIChildWndEx::GetRelatedTabGroup](#getrelatedtabgroup)||  
|[CMDIChildWndEx::GetTabbedPane](#gettabbedpane)|Gibt einen Zeiger auf eine eingebettete andockbaren Bereich, der in ein Dokument im Registerkartenformat konvertiert wurde.|  
|[CMDIChildWndEx::GetTabProxyWnd](#gettabproxywnd)|Gibt auf der Registerkarte Proxy-Fenster mit Registerkarten für Windows 7-Taskleiste nicht registriert.|  
|[CMDIChildWndEx::GetTaskbarPreviewWnd](#gettaskbarpreviewwnd)|Vom Framework aufgerufen, wenn er erhalten ein untergeordnetes Fenster (normalerweise ein Ansichts- oder Splitterfenster-Fenster), die auf Windows 7-Taskleiste-registerkartenminiaturansicht angezeigt werden muss.|  
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](#gettaskbarthumbnailcliprect)|Vom Framework aufgerufen, wenn er auf einen Teil des Clientbereichs des Fensters, als dieses Fensters Miniaturansicht in der Taskleiste angezeigt muss wird.|  
|`CMDIChildWndEx::GetThisClass`|Wird aufgerufen, durch das Framework um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMDIChildWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Wird aufgerufen, durch das Framework in einer QuickInfo für eine Symbolleisten-Schaltfläche abgerufen.|  
|[CMDIChildWndEx::InsertPane](#insertpane)|Registriert den angegebenen Bereich beim Dock-Manager.|  
|[CMDIChildWndEx::InvalidateIconicBitmaps](#invalidateiconicbitmaps)|Erklärt Elementsymbol Bitmap-Darstellung des untergeordneten MDI-Fensters.|  
|[CMDIChildWndEx::IsPointNearDockSite](#ispointneardocksite)|Bestimmt, ob ein angegebener Punkt in der Nähe der DockPosition ist.|  
|[CMDIChildWndEx::IsReadOnly](#isreadonly)|Gibt `TRUE` , wenn das Dokument, das in das untergeordnete Fenster angezeigt wird, schreibgeschützt ist. Andernfalls wird `FALSE` zurückgegeben.|  
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](#isregisteredwithtaskbartabs)|Gibt "true" zurück, wenn untergeordnete MDI-Fenster mit Registerkarten für Windows 7-Taskleiste erfolgreich registriert wurde.|  
|[CMDIChildWndEx::IsTabbedPane](#istabbedpane)|Gibt `TRUE` , wenn die untergeordneten MDI-Fensters einen andockbaren Bereich enthält. Andernfalls wird `FALSE` zurückgegeben.|  
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](#istaskbartabssupportenabled)|Erfahren Sie, ob das untergeordnete MDI-Fenster auf Windows 7-Taskleiste Registerkarten angezeigt werden kann.|  
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](#istaskbarthumbnailcliprectenabled)|Erfahren Sie, ob die automatische Auswahl von einem Teil des Clientbereichs des Fensters, als dieses Fensters Miniaturansicht in der Taskleiste anzeigen aktiviert oder deaktiviert ist.|  
|[CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags](#m_dwdefaulttaskbartabpropertyflags)|Eine Kombination von Flags, die durch das Framework der SetTaskbarTabProperties-Methode übergeben wird, wenn eine Registerkarte (untergeordnetes MDI) mit Windows 7-Taskleiste Registerkarten registriert wird. Die Standardkombination ist STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE.|  
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](#ongeticoniclivepreviewbitmap)|Vom Framework aufgerufen, wenn es muss sich um ein Bitmuster für Livevorschau der untergeordnete MDI-Fenster zu erhalten.|  
|[CMDIChildWndEx::OnGetIconicThumbnail](#ongeticonicthumbnail)|Vom Framework aufgerufen, wenn es muss sich um ein Bitmuster für Elementsymbol Miniaturansicht der untergeordnete MDI-Fenster zu erhalten.|  
|[CMDIChildWndEx::OnMoveMiniFrame](#onmoveminiframe)|Wird aufgerufen, durch das Framework ein Minirahmenfenster zu verschieben.|  
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](#onpresstaskbarthmbnailclosebutton)|Vom Framework aufgerufen, wenn der Benutzer die Schaltfläche "Schließen" auf der Taskleiste registerkartenminiaturansicht drückt...|  
|[CMDIChildWndEx::OnSetPreviewMode](#onsetpreviewmode)|Wird aufgerufen, durch das Framework zu beginnen oder Beenden der Seitenansicht.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](#ontaskbartabthumbnailactivate)|Vom Framework aufgerufen, wenn die Taskleiste-registerkartenminiaturansicht WM_ACTIVATE Nachricht verarbeiten soll.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](#ontaskbartabthumbnailmouseactivate)|Vom Framework aufgerufen, wenn die Taskleiste-registerkartenminiaturansicht WM_MOUSEACTIVATE Nachricht verarbeiten soll.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](#ontaskbartabthumbnailstretch)|Vom Framework aufgerufen, wenn es muss sich um ein Bitmuster für Windows 7-Taskleiste Registerkarte-Miniaturansicht der untergeordneten MDI-Fensters zu Strecken.|  
|[CMDIChildWndEx::OnUpdateFrameTitle](#onupdateframetitle)|Wird aufgerufen, durch das Framework beim Aktualisieren des Frame-Titels. (Überschreibt `CMDIChildWnd::OnUpdateFrameTitle`.)|  
|[CMDIChildWndEx::PaneFromPoint](#panefrompoint)|Gibt den Bereich, der den angegebenen Punkt enthält.|  
|`CMDIChildWndEx::PreTranslateMessage`|Wird von der [CWinApp](../../mfc/reference/cwinapp-class.md) -Klasse verwendet, um Fenstermeldungen zu übersetzen, bevor diese an die Windows-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) gesendet werden. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMDIChildWndEx::RecalcLayout](#recalclayout)|Berechnet das Layout des Fensters neu.|  
|[CMDIChildWndEx::RegisterTaskbarTab](#registertaskbartab)|Registriert untergeordnete MDI-Fenster mit Registerkarten für Windows 7-Taskleiste an.|  
|[CMDIChildWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|Entfernt einen Bereich von Dock-Manager.|  
|[CMDIChildWndEx::SetRelatedTabGroup](#setrelatedtabgroup)||  
|[CMDIChildWndEx::SetTaskbarTabActive](#settaskbartabactive)|Aktiviert die entsprechende Registerkarte der Windows 7-Taskleiste.|  
|[CMDIChildWndEx::SetTaskbarTabOrder](#settaskbartaborder)|Fügt ein untergeordnetes MDI-Objekt vor dem angegebenen Fensters auf Windows 7-Taskleiste Registerkarten.|  
|[CMDIChildWndEx::SetTaskbarTabProperties](#settaskbartabproperties)|Legt Eigenschaften für eine Registerkarte der Windows 7-Taskleiste fest.|  
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](#settaskbarthumbnailcliprect)|Wird intern aufgerufen, durch das Framework festzulegende Clippingrechteck an, wählen Sie einen Teil des Clientbereichs des Fensters, als dieses Fensters Miniaturansicht in der Taskleiste angezeigt.|  
|[CMDIChildWndEx::ShowPane](#showpane)||  
|[CMDIChildWndEx::UnregisterTaskbarTab](#unregistertaskbartab)|Entfernt untergeordnete MDI-Fenster von Registerkarten für Windows 7-Taskleiste an.|  
|[CMDIChildWndEx::UpdateTaskbarTabIcon](#updatetaskbartabicon)|Symbol "Tab" der Windows 7-Taskleiste wird aktualisiert.|  
  
## <a name="remarks"></a>Hinweise  
 Um erweiterte andockbaren Funktionen im MDI-Anwendungen nutzen zu können, leiten Sie die untergeordneten MDI-Fensterklasse der Anwendung aus `CMDIChildWndEx` anstelle von [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine Klasse von abgeleitet `CMDIChildWndEx`. Dieser Codeausschnitt ergibt sich aus der [VisualStudioDemo-Beispiel: MFC-Anwendung für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#3](../../mfc/codesnippet/cpp/cmdichildwndex-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)  
  
 [CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxMDIChildWndEx.h  
  
##  <a name="addpane"></a>CMDIChildWndEx::AddPane  
 Fügt einen Bereich hinzu.  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 Ein Zeiger auf den Bereich.  
  
 [in] `bTail`  
 `TRUE`So fügen Sie den Bereich an das Ende der Liste von Bereichen für Dock-Manager; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich beim Dock-Manager; erfolgreich registriert wurde andernfalls `FALSE`.  
  
##  <a name="addtabbedpane"></a>CMDIChildWndEx::AddTabbedPane  
 Fügt einen Bereich im Registerkartenformat hinzu.  
  
```  
void AddTabbedPane(CDockablePane* pControlBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 Ein Zeiger auf den Bereich.  
  
##  <a name="adjustdockinglayout"></a>CMDIChildWndEx::AdjustDockingLayout  
 Passt die am Layout des Docks an.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hdwp`  
 Handle für eine verzögerte Fenster Position-Struktur.  
  
##  <a name="canshowonmditabs"></a>CMDIChildWndEx::CanShowOnMDITabs  

  
```  
virtual BOOL CanShowOnMDITabs();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="canshowonwindowslist"></a>CMDIChildWndEx::CanShowOnWindowsList  
 Gibt an, ob der Name der MDI-untergeordneten Fenster kann, in angezeigt werden der [CMFCWindowsManagerDialog Klasse](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) (Dialogfeld).  
  
```  
virtual BOOL CanShowOnWindowsList();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn im Fenster angezeigt werden kann die **Windows** (Dialogfeld), andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode in einer abgeleiteten Klasse überschreiben und zurückgeben `FALSE` , wenn das Fenster nicht soll, können Sie in angezeigt werden der **Windows** (Dialogfeld). Diese Funktion wird aufgerufen, von `CMFCWindowsManagerDialog`.  
  
##  <a name="dockpane"></a>CMDIChildWndEx::DockPane  
 Dockt einen Bereich an.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf den Bereich.  
  
 [in] `nDockBarID`  
 Die ID des Bereichs.  
  
 [in] `lpRect`  
 Ein Zeiger auf ein Rechteck.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpRect` Parameter wird nicht verwendet.  
  
##  <a name="dockpaneleftof"></a>CMDIChildWndEx::DockPaneLeftOf  
 Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>Parameter  
 `pBar`  
 Ein Zeiger auf den Bereich, der angedockt werden.  
  
 `pLeftOf`  
 Ein Zeiger auf den Bereich, der als Bezugspunkt dient.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Bei Erfolg `FALSE` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nimmt Bereich gemäß `pBar` und Dockt es auf der linken Seite des Bereichs von angegebenen `pLeftOf`.  
  
 Rufen Sie diese Methode, wenn Sie mehrere Informationsbereiche in einer vordefinierten Reihenfolge andocken möchten.  
  
##  <a name="enableautohidepanes"></a>CMDIChildWndEx::EnableAutoHidePanes  
 Ermöglicht das automatischen Ausblendemodus für Bereiche, wenn sie sich an den angegebenen Seiten des Fensters angedockt sind.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwDockStyle`  
 Gibt die Seiten des Hauptrahmenfenster aktiviert ist. Verwenden Sie eine oder mehrere der folgenden Flags.  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist. andernfalls `FALSE`.  
  
##  <a name="enabledocking"></a>CMDIChildWndEx::EnableDocking  
 Ermöglicht das Andocken von untergeordneten Fensters zum Hauptframe.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwDockStyle`  
 Gibt die andockbare Ausrichtung zu aktivieren.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zum Hauptframe andockbaren Ausrichtung zu aktivieren. Sie können eine Kombination von Flags CBRS_ALIGN_ übergeben (Weitere Informationen finden Sie unter [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
##  <a name="getdockingmanager"></a>CMDIChildWndEx::GetDockingManager  

  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdocumentname"></a>CMDIChildWndEx::GetDocumentName  
 Gibt den Namen des Dokuments, das in der untergeordneten MDI-Fensters angezeigt wird.  
  
```  
virtual LPCTSTR GetDocumentName(CObject** pObj);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Zeichenfolge, die den Namen eines Dokuments enthält.  
  
### <a name="remarks"></a>Hinweise  
 Es ist ein Dokument, das die untergeordneten MDI-Fensters angezeigt. Im Allgemeinen zeigt das Fenster Daten, die aus geladen werden, oder in einer Datei gespeichert. Der Name des Dokuments wird daher der Name der Datei. Die standardmäßige Implementierung des `GetDocumentName` gibt eine Zeichenfolge, die aus abgerufen `CDocument::GetPathName`.  
  
 Wenn das Fenster ein Dokument angezeigt wird, die nicht aus einer Datei geladen wird, überschreiben Sie diese Methode in einer abgeleiteten Klasse, und eine eindeutige Dokument-ID zurück.  
  
 `GetDocumentName`wird vom Framework aufgerufen werden, wenn den Status aller geöffneten Dokumente gespeichert. Die zurückgegebene Zeichenfolge wird in der Registrierung geschrieben.  
  
 Wenn das Framework Zustand später wiederherstellen, den Namen des Dokuments aus der Registrierung gelesen und übergeben [CMDIFrameWndEx::CreateDocumentWindow](../../mfc/reference/cmdiframewndex-class.md#createdocumentwindow). Überschreiben Sie diese Methode in einer [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)-abgeleitete Klasse, und erstellen oder öffnen Sie ein Dokument, das diesen Namen aufweist, und in die Datei mit diesem Namen zu lesen. Wenn das Dokument nicht auf eine Datei basiert, erstellen Sie das Dokument anhand der Dokument-ID selbst. Sie sollten die obigen Aktionen ausführen, nur, wenn Sie beabsichtigen, speichern und Wiederherstellen von Dokumenten.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der `GetDocumentName`-Methode gezeigt. Dieser Codeausschnitt ergibt sich aus der [VisualStudioDemo-Beispiel: MFC-Anwendung für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#17](../../mfc/codesnippet/cpp/cmdichildwndex-class_2.cpp)]  
  
##  <a name="getframeicon"></a>CMDIChildWndEx::GetFrameIcon  
 Wird aufgerufen, durch das Framework das Symbol des untergeordneten MDI-Fensters abgerufen.  
  
```  
virtual HICON GetFrameIcon() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das Symbol "Fenster".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework, um zu bestimmen, welches Symbol auf der MDI-Registerkarte angezeigt werden sollen, die die untergeordneten MDI-Rahmenfenster enthält.  
  
 Standardmäßig gibt diese Methode das Symbol "Fenster". Überschreiben Sie `GetFrameIcon` in einem `CMDIChildWndEx`-abgeleitete Klasse, um dieses Verhalten anzupassen.  
  
##  <a name="getframetext"></a>CMDIChildWndEx::GetFrameText  
 Wird aufgerufen, durch das Framework zum Abrufen des Texts für die untergeordneten MDI-Fensters.  
  
```  
virtual CString GetFrameText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Fenstertext Frame enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework, um zu bestimmen, welcher Text auf der MDI-Registerkarte angezeigt werden sollen, die die untergeordneten MDI-Rahmenfenster enthält.  
  
 Standardmäßig gibt diese Methode den Fenstertext. Überschreiben Sie `GetFrameText` in einem `CMDIChildWndEx`-abgeleitete Klasse, um dieses Verhalten anzupassen.  
  
##  <a name="getpane"></a>CMDIChildWndEx::GetPane  
 Sucht nach einem Bereich durch das angegebene Steuerelement-ID.  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Die Steuerelement-ID des Bereichs zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Bereich Wenn gefunden, andernfalls `NULL`.  
  
##  <a name="getrelatedtabgroup"></a>CMDIChildWndEx::GetRelatedTabGroup  

  
```  
CMFCTabCtrl* GetRelatedTabGroup();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettabbedpane"></a>CMDIChildWndEx::GetTabbedPane  
 Gibt ein Zeiger auf einen andockbaren Bereich, die Teil einer Gruppe von MDI Dokumente im Registerkartenformat zurück.  
  
```  
CDockablePane* GetTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf einen andockbaren Bereich, der eine Gruppe von MDI gehört, die Dokumente im Registerformat.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>CMDIChildWndEx::GetToolbarButtonToolTipText  
 Wird aufgerufen, durch das Framework in einer QuickInfo für eine Symbolleisten-Schaltfläche abgerufen.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton*, 
    CString&);
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die QuickInfo angezeigt wurde. Die Standardimplementierung gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie benutzerdefinierte QuickInfos für Symbolleisten-Schaltflächen angezeigt werden soll.  
  
##  <a name="insertpane"></a>CMDIChildWndEx::InsertPane  
 Registriert den angegebenen Bereich beim Dock-Manager.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 Ein Zeiger auf den Bereich eingefügt.  
  
 [in] `pTarget`  
 Ein Zeiger auf angrenzenden Bereich.  
  
 [in] `bAfter`  
 Wenn `TRUE`, `pControlBar` eingefügt, nachdem `pTarget`. Wenn `FALSE`, `pControlBar` eingefügt wird, bevor Sie `pTarget`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist, `FALSE` andernfalls.  
  
##  <a name="ispointneardocksite"></a>CMDIChildWndEx::IsPointNearDockSite  
 Bestimmt, ob ein angegebener Punkt in der Nähe der DockPosition ist.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Der angegebene Punkt.  
  
 [in] `dwBarAlignment`  
 Gibt an, welche Kante, die in der Nähe der Punkt ist. Mögliche Werte sind `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, und`CBRS_ALIGN_BOTTOM`  
  
 [in] `bOuterEdge`  
 `TRUE`Wenn der Punkt in der Nähe von den äußeren Rahmen der DockPosition ist; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Punkt in der Nähe der DockPosition ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Punkt ist in der Nähe der DockPosition auf, wenn es innerhalb der Vertraulichkeit in Dock-Manager festgelegt ist. Die Vertraulichkeit der Standardwert beträgt 15 Pixel.  
  
##  <a name="isreadonly"></a>CMDIChildWndEx::IsReadOnly  
 Gibt an, ob das Dokument, das in das untergeordnete Fenster angezeigt wird, schreibgeschützt ist.  
  
```  
virtual BOOL IsReadOnly();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Dokument schreibgeschützt ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird verwendet, um zu verhindern, dass nur-Lese Dokumente zu speichern.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Überschreiben der `IsReadOnly` Methode. Dieser Codeausschnitt ergibt sich aus der [VisualStudioDemo-Beispiel: MFC-Anwendung für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#2](../../mfc/codesnippet/cpp/cmdichildwndex-class_3.cpp)]  
  
##  <a name="istabbedpane"></a>CMDIChildWndEx::IsTabbedPane  
 Gibt an, ob die untergeordneten MDI-Fensters einen andockbaren Bereich enthält.  
  
```  
BOOL IsTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die untergeordneten MDI-Fensters einen andockbaren Bereich, der in ein Dokument im Registerkartenformat konvertiert wurde enthält. andernfalls `FALSE`.  
  
##  <a name="onmoveminiframe"></a>CMDIChildWndEx::OnMoveMiniFrame  
 Wird aufgerufen, durch das Framework ein Minirahmenfenster zu verschieben.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFrame`  
 Ein Zeiger auf ein Minirahmenfenster.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich, andernfalls ist `FALSE`.  
  
##  <a name="onsetpreviewmode"></a>CMDIChildWndEx::OnSetPreviewMode  
 Wird aufgerufen, durch das Framework zu beginnen oder Beenden der Seitenansicht.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bPreview`  
 Wenn `TRUE`, geben Sie die Seitenansicht. Wenn `FALSE`, Seitenansicht beenden.  
  
 [in] `pState`  
 Ein Zeiger auf die Seitenansicht-Status-Struktur.  
  
##  <a name="onupdateframetitle"></a>CMDIChildWndEx::OnUpdateFrameTitle  
 Wird aufgerufen, durch das Framework beim Aktualisieren des Frame-Titels.  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAddToTitle`  
 Wenn `TRUE`, fügen Sie den Namen des Dokuments an den Titel.  
  
##  <a name="panefrompoint"></a>CMDIChildWndEx::PaneFromPoint  
 Gibt den Bereich, der den angegebenen Punkt enthält.  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar,  
    CRuntimeClass* pRTCBarType) const;  
  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Gibt den Punkt in Bildschirmkoordinaten, um zu überprüfen.  
  
 [in] `nSensitivity`  
 Erhöhen Sie den Suchbereich, indem Sie diese Menge. Ein Bereich erfüllt die Suchkriterien, fällt der angegebene Punkt in der höheren Bereich.  
  
 [in] `bExactBar`  
 `TRUE`ignoriert die `nSensitivity` Parameter ist, andernfalls `FALSE`.  
  
 [in] `pRTCBarType`  
 Wenn dies nicht der `NULL`, sucht die Methode nur Bereiche des angegebenen Typs.  
  
 [in] `dwAlignment`  
 Wenn Sie ein Bereich am angegebenen Punkt gefunden wird, enthält dieser Parameter den Rand des Bereichs, der den angegebenen Punkt am nächsten gelegenen war. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CBasePane`-abgeleitetes Objekt, das den angegebenen Punkt enthält oder `NULL` Wenn kein Bereich gefunden wurde.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zu bestimmen, ob ein Bereich auf den angegebenen Punkt gemäß den angegebenen Bedingungen wie z. B. Laufzeitklasse und Sichtbarkeit enthält.  
  
 Wenn die Funktion zurückgibt und ein Bereich gefunden wurde, `dwAlignment` die Ausrichtung des angegebenen Punkt enthält. Beispielsweise war der Punkt am Anfang des Bereichs am nächsten gelegenen `dwAlignment` festgelegt ist, um `CBRS_ALIGN_TOP`.  
  
##  <a name="recalclayout"></a>CMDIChildWndEx::RecalcLayout  
 Berechnet das Layout des Fensters neu.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bNotify`  
 Wenn `TRUE`, das aktive direkte-Element für das Fenster erhält eine Benachrichtigung von der layoutänderung.  
  
##  <a name="removepanefromdockmanager"></a>CMDIChildWndEx::RemovePaneFromDockManager  
 Entfernt einen Bereich von Dock-Manager.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 Ein Zeiger auf den Bereich zu entfernen.  
  
 [in] `bDestroy`  
 Wenn `TRUE`, entfernte Bereich zerstört wird.  
  
 [in] `bAdjustLayout`  
 Wenn `TRUE`, passen Sie das Layout des Docks sofort.  
  
 [in] `bAutoHide`  
 Wenn `TRUE`, am Layout des Docks bezieht sich auf die Liste der leisten zum automatischen ausblenden. Wenn `FALSE`, am Layout des Docks bezieht sich auf die Liste der regulären Bereiche.  
  
 [in] `pBarReplacement`  
 Ein Zeiger auf einen Bereich, der Bereich entfernten ersetzt.  
  
##  <a name="setrelatedtabgroup"></a>CMDIChildWndEx::SetRelatedTabGroup  

  
```  
void SetRelatedTabGroup(CMFCTabCtrl* p);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `p`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="showpane"></a>CMDIChildWndEx::ShowPane  

  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 [in] `bShow`  
 [in] `bDelay`  
 [in] `bActivate`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="updatetaskbartabicon"></a>CMDIChildWndEx::UpdateTaskbarTabIcon  
 Symbol "Tab" der Windows 7-Taskleiste wird aktualisiert.  
  
```  
virtual void UpdateTaskbarTabIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 `hIcon`  
 Ein Handle für ein Symbol auf der Registerkarte der Windows 7-Taskleiste angezeigt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="unregistertaskbartab"></a>CMDIChildWndEx::UnregisterTaskbarTab  
 Entfernt das untergeordnete MDI-Fenster von Registerkarten für Windows 7-Taskleiste an.  
  
```  
void UnregisterTaskbarTab(BOOL bCheckRegisteredMDIChildCount = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bCheckRegisteredMDIChildCount`  
 Gibt an, ob diese Funktion die Anzahl der untergeordnete MDI-Fenster, die mit MDI-Registerkarten registriert überprüfen muss. Wenn diese Zahl 0 ist, entfernt diese Funktion das Clippingrechteck an, aus der Anwendung Taskleistenminiaturansicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settaskbarthumbnailcliprect"></a>CMDIChildWndEx::SetTaskbarThumbnailClipRect  
 Vom Framework aufgerufen wird, legen Sie das Clippingrechteck an, wählen Sie einen Teil des Clientbereichs des Fensters, als dieses Fensters Miniaturansicht in der Taskleiste angezeigt.  
  
```  
virtual BOOL SetTaskbarThumbnailClipRect(CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Gibt das neue Clippingrechteck an. Wenn das Rechteck leer oder null ist, wird das Clipping entfernt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settaskbartabproperties"></a>CMDIChildWndEx::SetTaskbarTabProperties  
 Legt Eigenschaften für eine Registerkarte der Windows 7-Taskleiste fest.  
  
```  
void SetTaskbarTabProperties(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Eine Kombination von STPFLAG-Werten. Weitere Informationen finden Sie unter [itaskbarlist4:: Settabproperties](http://msdn.microsoft.com/library/dd562049\(vs.85\).aspx).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settaskbartaborder"></a>CMDIChildWndEx::SetTaskbarTabOrder  
 Fügt das untergeordnete MDI-Fenster, bevor das angegebene Fenster auf Windows 7-Taskleiste Registerkarten ein.  
  
```  
void SetTaskbarTabOrder(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndBefore`  
 Ein Zeiger auf die untergeordneten MDI-Fensters, dessen Miniaturansicht auf der linken Seite eingefügt wird. In diesem Fenster muss bereits registriert werden, über `RegisterTaskbarTab`. Wenn dieser Wert ist `NULL`, die neue Miniaturansicht wird bis zum Ende der Liste hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settaskbartabactive"></a>CMDIChildWndEx::SetTaskbarTabActive  
 Aktiviert die entsprechende Registerkarte für die Windows 7-Taskleiste an.  
  
```  
void SetTaskbarTabActive();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="registertaskbartab"></a>CMDIChildWndEx::RegisterTaskbarTab  
 Registriert das untergeordnete MDI-Fenster mit Registerkarten für Windows 7-Taskleiste an.  
  
```  
virtual void RegisterTaskbarTab(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndBefore`  
 Ein Zeiger auf die untergeordneten MDI-Fensters, dessen Miniaturansicht auf der linken Seite eingefügt wird. In diesem Fenster muss bereits registriert werden, über `RegisterTaskbarTab`. Wenn dieser Wert ist `NULL`, die neue Miniaturansicht wird bis zum Ende der Liste hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ontaskbartabthumbnailstretch"></a>CMDIChildWndEx::OnTaskbarTabThumbnailStretch  
 Vom Framework aufgerufen, wenn es muss sich um ein Bitmuster für Windows 7-Taskleiste Registerkarte Miniaturansicht der untergeordneten MDI-Fensters zu Strecken.  
  
```  
virtual BOOL OnTaskbarTabThumbnailStretch(
    HBITMAP hBmpDst,  
    const CRect& rectDst,  
    HBITMAP hBmpSrc,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `hBmpDst`  
 Ein Handle für eine Zielbitmap.  
  
 `rectDst`  
 Gibt die Zielrechtecks an.  
  
 `hBmpSrc`  
 Ein Handle für eine Quellbitmap.  
  
 `rectSrc`  
 Gibt das Quellrechteck an.  
  
### <a name="remarks"></a>Hinweise  
 Requirementher oder ihm ihm ihm ihm ihm ihm ihm **:** afxmdichildwndex.h  
  
##  <a name="ontaskbartabthumbnailmouseactivate"></a>CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate  
 Vom Framework aufgerufen, wenn die Taskleiste-registerkartenminiaturansicht WM_MOUSEACTIVATE Nachricht verarbeiten soll.  
  
```  
virtual int OnTaskbarTabThumbnailMouseActivate(
    CWnd* pDesktopWnd,  
    UINT nHitTest,  
    UINT message);
```  
  
### <a name="parameters"></a>Parameter  
 `pDesktopWnd`  
 Gibt einen Zeiger auf das übergeordnete Fenster des Fensters aktiviert wird. Der Zeiger kann temporär sein und sollte nicht gespeichert werden.  
  
 `nHitTest`  
 Gibt an, die Ortskennzahl Treffertests. Ein Treffertest ist ein Test, der die Position des Cursors bestimmt.  
  
 `message`  
 Gibt die Anzahl der Maus-Nachricht.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung aktiviert die zugehörigen untergeordneten MDI-Rahmens.  
  
##  <a name="ontaskbartabthumbnailactivate"></a>CMDIChildWndEx::OnTaskbarTabThumbnailActivate  
 Vom Framework aufgerufen, wenn die Taskleiste-registerkartenminiaturansicht WM_ACTIVATE Nachricht verarbeiten soll.  
  
```  
virtual void OnTaskbarTabThumbnailActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>Parameter  
 `nState`  
 Gibt an, ob die `CWnd` aktiviert bzw. deaktiviert wird.  
  
 `pWndOther`  
 Zeiger auf die `CWnd` aktiviert bzw. deaktiviert. Der Zeiger kann `NULL`, und es kann temporär sein.  
  
 `bMinimized`  
 Gibt den minimierten Zustand der `CWnd` aktiviert bzw. deaktiviert. Der Wert `TRUE` gibt an, das Fenster wird minimiert.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung aktiviert die zugehörigen untergeordneten MDI-Rahmens.  
  
##  <a name="onpresstaskbarthmbnailclosebutton"></a>CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton  
 Vom Framework aufgerufen, wenn der Benutzer die Schaltfläche "Schließen" auf der Taskleiste-registerkartenminiaturansicht drückt.  
  
```  
virtual void OnPressTaskbarThmbnailCloseButton();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ongeticonicthumbnail"></a>CMDIChildWndEx::OnGetIconicThumbnail  
 Vom Framework aufgerufen, wenn eine Bitmap für das Elementsymbol Miniaturansicht des untergeordneten MDI-Fensters abgerufen werden muss.  
  
```  
virtual HBITMAP OnGetIconicThumbnail(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `nWidth`  
 Gibt die Breite der Bitmap erforderlich.  
  
 `nHeight`  
 Gibt die Höhe der Bitmap erforderlich.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ongeticoniclivepreviewbitmap"></a>CMDIChildWndEx::OnGetIconicLivePreviewBitmap  
 Vom Framework aufgerufen, wenn es muss sich um ein Bitmuster für Livevorschau der untergeordneten MDI-Fensters zu erhalten.  
  
```  
virtual HBITMAP OnGetIconicLivePreviewBitmap(
    BOOL bIsMDIChildActive,  
    CPoint& ptLocation);
```  
  
### <a name="parameters"></a>Parameter  
 `bIsMDIChildActive`  
 Dieser Parameter ist `TRUE` , wenn die Bitmap für die untergeordneten MDI-Fensters angefordert wird, die derzeit aktiv ist und das Hauptfenster wird nicht minimiert. In diesem Fall die standardverarbeitung nimmt eine Momentaufnahme des Hauptfensters.  
  
 `ptLocation`  
 Gibt den Speicherort der Bitmap in der Main (oberste Ebene) Fenster Clientkoordinaten. Dieser Punkt muss vom aufgerufenen bereitgestellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Verarbeitet, zurück, wenn ein Handle auf eine gültige 32bpp-Bitmap andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode in einer abgeleiteten Klasse überschreiben, und geben Sie eine gültige 32bpp-Bitmap für Livevorschau der untergeordneten MDI-Fensters zurück. Diese Methode wird aufgerufen, nur, wenn das untergeordnete MDI-Fenster auf Registerkarten für Windows 7-Taskleiste angezeigt wird. Wenn Sie zurückkehren, `NULL`, MFC die Standardhandler aufruft und mithilfe von Bitmaps abruft `PrintClient` oder `PrintWindow`.  
  
##  <a name="m_dwdefaulttaskbartabpropertyflags"></a>CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags  
 Eine Kombination von Flags, die durch das Framework zu übergeben, wird die `SetTaskbarTabProperties` Methode, wenn Sie eine Registerkarte (untergeordnetes MDI) mit Windows 7-Taskleiste Registerkarten registriert wird.  
  
```  
AFX_IMPORT_DATA static DWORD m_dwDefaultTaskbarTabPropertyFlags;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Standardkombination ist STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE.  
  
##  <a name="istaskbarthumbnailcliprectenabled"></a>CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled  
 Erfahren Sie, ob die automatische Auswahl von einem Teil des Clientbereichs des Fensters, als dieses Fensters Miniaturansicht in der Taskleiste anzeigen aktiviert oder deaktiviert ist.  
  
```  
BOOL IsTaskbarThumbnailClipRectEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` wenn automatische Auswahl eines Teils des Clientbereichs des Fensters angezeigt, andernfalls aktiviert wird `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="istaskbartabssupportenabled"></a>CMDIChildWndEx::IsTaskbarTabsSupportEnabled  
 Erfahren Sie, ob das untergeordnete MDI-Fenster auf Windows 7-Taskleiste Registerkarten angezeigt werden kann.  
  
```  
BOOL IsTaskbarTabsSupportEnabled();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die untergeordneten MDI-Fensters auf Windows 7-Taskleiste Registerkarten angezeigt werden kann; `FALSE` Wenn untergeordneten MDI-Fensters nicht auf Windows 7-Taskleiste Registerkarten angezeigt werden kann.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isregisteredwithtaskbartabs"></a>CMDIChildWndEx::IsRegisteredWithTaskbarTabs  
 Gibt `TRUE` , wenn das untergeordnete MDI-Fenster mit Registerkarten für Windows 7-Taskleiste erfolgreich registriert wurde.  
  
```  
BOOL IsRegisteredWithTaskbarTabs();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das untergeordnete MDI-Fenster mit Registerkarten für Windows 7-Taskleiste; registriert ist andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="invalidateiconicbitmaps"></a>CMDIChildWndEx::InvalidateIconicBitmaps  
 Erklärt eine Elementsymbol Bitmapdarstellung eines untergeordneten MDI-Elements.  
  
```  
BOOL InvalidateIconicBitmaps();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `FALSE` wenn Unterstützung für Windows 7-Taskleiste deaktiviert ist oder das untergeordnete MDI-Element nicht, mit Windows 7-Taskleiste Registerkarten registriert ist; andernfalls `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Sollte aufgerufen werden, wenn der aktive Inhalte oder die Größe eines untergeordneten MDI-geändert hat.  
  
##  <a name="gettaskbarthumbnailcliprect"></a>CMDIChildWndEx::GetTaskbarThumbnailClipRect  
 Vom Framework aufgerufen, wenn er auf einen Teil des Clientbereichs des Fensters, als dieses Fensters Miniaturansicht in der Taskleiste angezeigt muss wird.  
  
```  
virtual CRect GetTaskbarThumbnailClipRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Rechteck in Windows-Koordinaten. Dieses Rechteck ist, das den Clientbereich des Frames oberster Ebene zugeordnet. Das Rechteck sollten, deaktivieren Sie das Clippingrechteck leer sein.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettaskbarpreviewwnd"></a>CMDIChildWndEx::GetTaskbarPreviewWnd  
 Vom Framework aufgerufen, wenn er erhalten ein untergeordnetes Fenster (normalerweise ein Ansichts- oder Splitterfenster-Fenster) auf einem Windows 7-Taskleiste-registerkartenminiaturansicht angezeigt werden muss.  
  
```  
virtual CWnd* GetTaskbarPreviewWnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Sollte einen gültigen Zeiger auf Zurückgeben einer `CWnd` Objekt, deren Vorschau soll, auf die Registerkarte für eine Windows 7-Taskleiste angezeigt werden im Zusammenhang mit diesem untergeordnete MDI-Fenster. Die Standardimplementierung gibt ein untergeordnetes Fenster von diesem untergeordnete MDI-Fenster mit AFX_IDW_PANE_FIRST Kontroll-ID (ist in der Regel eine `CView`-Klasse).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettabproxywnd"></a>CMDIChildWndEx::GetTabProxyWnd  
 Gibt die Registerkarte Proxy-Fenster mit Registerkarten für Windows 7-Taskleiste registriert.  
  
```  
CMDITabProxyWnd* GetTabProxyWnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CMDITabProxyWnd` -Objekt, das mit Windows 7-Taskleiste Registerkarten registriert ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabletaskbarthumbnailcliprect"></a>CMDIChildWndEx::EnableTaskbarThumbnailClipRect  
 Aktiviert oder deaktiviert die automatische Auswahl von einem Teil des Clientbereichs des Fensters, als dieses Fensters Miniaturansicht in der Taskleiste angezeigt.  
  
```  
void EnableTaskbarThumbnailClipRect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob ( `TRUE`), oder deaktivieren ( `FALSE`) automatischen Auswahl eines Teils des Clientbereichs des Fensters angezeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="canshowontaskbartabs"></a>CMDIChildWndEx::CanShowOnTaskBarTabs  
 Das Framework angewiesen wird, ob diese untergeordneten MDI-Fensters auf Windows 7-Taskleiste Registerkarten angezeigt werden kann.  
  
```  
virtual BOOL CanShowOnTaskBarTabs();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Inhalt des untergeordneten MDI-Fensters auf Miniaturansichten für Windows 7-Taskleiste angezeigt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode in einer abgeleiteten Klasse überschreiben und zurückgeben `FALSE` , die Darstellung von diesem untergeordnete MDI-Fenster auf Windows 7-Taskleiste Registerkarten deaktivieren.  
  
##  <a name="activatetoplevelframe"></a>CMDIChildWndEx::ActivateTopLevelFrame  
 Wird aufgerufen, durch das Framework den obersten Ebene Frame zu aktivieren, wenn die Anwendung über eine Registerkarte Taskleiste aktiviert ist.  
  
```  
virtual void ActivateTopLevelFrame();
```  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMDIChildWnd-Klasse](../../mfc/reference/cmdichildwnd-class.md)   
 [CMFCWindowsManagerDialog-Klasse](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)   
 [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md)
