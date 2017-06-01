---
title: CMDIChildWndEx-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWndEx class
- ActivateFrame method
- PreTranslateMessage method
- GetThisClass method
- CreateObject method
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
caps.latest.revision: 35
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
ms.openlocfilehash: 016de8fdade75376f9f081539c0f160a6502bc37
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmdichildwndex-class"></a>CMDIChildWndEx-Klasse
Die `CMDIChildWndEx` -Klasse stellt die Funktionalität eines Windows untergeordneten Fenster der multiple Document Interface (MDI). Es erweitert die Funktionalität von [CMDIChildWnd-Klasse](../../mfc/reference/cmdichildwnd-class.md). Das Framework benötigt diese Klasse, wenn eine MDI-Anwendung bestimmte MFC-Klassen verwendet.  
 
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  

  
## <a name="syntax"></a>Syntax  
  
```  
class CMDIChildWndEx : public CMDIChildWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDIChildWndEx::ActivateTopLevelFrame](#activatetoplevelframe)|Wird intern aufgerufen, durch das Framework obersten Ebenen Rahmen zu aktivieren, wenn die Anwendung über eine Registerkarte Taskleiste aktiviert werden soll.|  
|`CMDIChildWndEx::AddDockSite`|Diese Methode wird nicht verwendet oder implementiert.|  
|[CMDIChildWndEx::AddPane](#addpane)|Fügt einen Bereich hinzu.|  
|[CMDIChildWndEx::AddTabbedPane](#addtabbedpane)|Fügt ein Fenster mit Registerkarten.|  
|[CMDIChildWndEx::AdjustDockingLayout](#adjustdockinglayout)|Passt die andocklayout an.|  
|[CMDIChildWndEx::CanShowOnMDITabs](#canshowonmditabs)||  
|[CMDIChildWndEx::CanShowOnTaskBarTabs](#canshowontaskbartabs)|Teilt dem Framework mit, ob dieser untergeordneten MDI-Fensters auf Windows 7-Taskleiste Registerkarten angezeigt werden kann.|  
|[CMDIChildWndEx::CanShowOnWindowsList](#canshowonwindowslist)|Gibt `TRUE` Wenn der Name der MDI-untergeordneten Fenster kann, in angezeigt werden der [CMFCWindowsManagerDialog Klasse](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) (Dialogfeld). Andernfalls wird `FALSE` zurückgegeben.|  
|`CMDIChildWndEx::CreateObject`|Aufgerufen, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMDIChildWndEx::DockPane](#dockpane)|Wird einen Bereich angedockt.|  
|[CMDIChildWndEx::DockPaneLeftOf](#dockpaneleftof)|Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.|  
|[CMDIChildWndEx::EnableAutoHidePanes](#enableautohidepanes)|Ermöglicht das automatische Ausblenden Modus für Bereiche, wenn diese an den angegebenen Seiten des Fensters angedockt sind.|  
|[CMDIChildWndEx::EnableDocking](#enabledocking)|Ermöglicht das Andocken des untergeordneten Fensters Hauptframe.|  
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](#enabletaskbarthumbnailcliprect)|Aktiviert oder deaktiviert die automatische Auswahl von einem Teil des Fensters Clientbereich des Fensters Miniaturansicht in der Taskleiste angezeigt.|  
|[CMDIChildWndEx::GetDockingManager](#getdockingmanager)||  
|[CMDIChildWndEx::GetDocumentName](#getdocumentname)|Gibt den Namen des Dokuments, das in der untergeordneten MDI-Fensters angezeigt wird.|  
|[CMDIChildWndEx::GetFrameIcon](#getframeicon)|Vom Framework aufgerufen wird zum Abrufen von untergeordneten MDI-Symbols.|  
|[CMDIChildWndEx::GetFrameText](#getframetext)|Aufgerufen, um den Text für die untergeordneten MDI-Fensters abzurufen.|  
|[CMDIChildWndEx::GetPane](#getpane)|Sucht einen Bereich von der angegebenen Steuerelement-ID|  
|[CMDIChildWndEx::GetRelatedTabGroup](#getrelatedtabgroup)||  
|[CMDIChildWndEx::GetTabbedPane](#gettabbedpane)|Gibt einen Zeiger auf eine eingebettete andockbaren Bereich, der ein Dokument im Registerkartenformat konvertiert wurde.|  
|[CMDIChildWndEx::GetTabProxyWnd](#gettabproxywnd)|Gibt Registerkarte Proxy-Fenster mit Registerkarten für Windows 7-Taskleiste nicht registriert.|  
|[CMDIChildWndEx::GetTaskbarPreviewWnd](#gettaskbarpreviewwnd)|Vom Framework aufgerufen, wenn ein untergeordnetes Fenster (in der Regel ein Fenster anzeigen oder den Splitter) auf Windows 7-Taskleiste Registerkarte Miniaturansicht angezeigt werden abgerufen werden muss.|  
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](#gettaskbarthumbnailcliprect)|Vom Framework aufgerufen, wenn einen Teil des Clientbereichs des Fensters Miniaturansicht in der Taskleiste anzeigen eines Fensters aktivieren muss.|  
|`CMDIChildWndEx::GetThisClass`|Aufgerufen, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMDIChildWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Aufgerufen, um eine QuickInfo für eine Symbolleisten-Schaltfläche abzurufen.|  
|[CMDIChildWndEx::InsertPane](#insertpane)|Registriert den angegebenen Bereich der docking-Manager.|  
|[CMDIChildWndEx::InvalidateIconicBitmaps](#invalidateiconicbitmaps)|Erklärt iconic Bitmap-Darstellung des untergeordneten MDI-Fensters.|  
|[CMDIChildWndEx::IsPointNearDockSite](#ispointneardocksite)|Bestimmt, ob es sich bei ein angegebenen Punkt in der Nähe der Dock-Website ist.|  
|[CMDIChildWndEx::IsReadOnly](#isreadonly)|Gibt `TRUE` , wenn das Dokument in das untergeordnete Fenster angezeigt wird, schreibgeschützt ist. Andernfalls wird `FALSE` zurückgegeben.|  
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](#isregisteredwithtaskbartabs)|Gibt TRUE zurück, wenn die untergeordneten MDI-Formulars mit Windows 7-Taskleiste Registerkarten erfolgreich registriert wurde.|  
|[CMDIChildWndEx::IsTabbedPane](#istabbedpane)|Gibt `TRUE` enthält die untergeordneten MDI-Fensters einen andockbaren Bereich. Andernfalls wird `FALSE` zurückgegeben.|  
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](#istaskbartabssupportenabled)|Erfahren Sie, ob die untergeordneten MDI-Fensters auf Windows 7-Taskleiste Registerkarten angezeigt werden kann.|  
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](#istaskbarthumbnailcliprectenabled)|Erfahren Sie, ob die automatische Auswahl eines Teils des Clientbereichs des Fensters Miniaturansicht in der Taskleiste anzeigen eines Fensters aktiviert oder deaktiviert ist.|  
|[CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags](#m_dwdefaulttaskbartabpropertyflags)|Eine Kombination von Flags, die vom Framework an die SetTaskbarTabProperties-Methode übergeben wird, wenn eine Registerkarte (MDI-untergeordnet) mit Windows 7-Taskleiste Registerkarten registriert wird. Die Standardkombination ist STPF_USEAPPTHUMBNAILWHENACTIVE | STPF_USEAPPPEEKWHENACTIVE.|  
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](#ongeticoniclivepreviewbitmap)|Vom Framework aufgerufen, wenn eine Bitmap für die live-Vorschau der untergeordneten MDI-Formulars abgerufen werden muss.|  
|[CMDIChildWndEx::OnGetIconicThumbnail](#ongeticonicthumbnail)|Vom Framework aufgerufen, wenn eine Bitmap für iconic-Miniaturansicht der untergeordneten MDI-Formulars abgerufen werden muss.|  
|[CMDIChildWndEx::OnMoveMiniFrame](#onmoveminiframe)|Aufgerufen, um ein Minirahmenfenster zu verschieben.|  
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](#onpresstaskbarthmbnailclosebutton)|Vom Framework aufgerufen, wenn der Benutzer die Schaltfläche "Schließen" auf der Taskleiste Registerkarte Miniaturansicht drückt...|  
|[CMDIChildWndEx::OnSetPreviewMode](#onsetpreviewmode)|Vom Framework aufgerufen wird, starten oder Beenden der Seitenansicht angezeigt.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](#ontaskbartabthumbnailactivate)|Wird vom Framework aufgerufen, wenn die Taskleiste Registerkarte Miniaturansicht WM_ACTIVATE Nachricht verarbeiten soll.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](#ontaskbartabthumbnailmouseactivate)|Wird vom Framework aufgerufen, wenn die Taskleiste Registerkarte Miniaturansicht WM_MOUSEACTIVATE Nachricht verarbeiten soll.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](#ontaskbartabthumbnailstretch)|Vom Framework aufgerufen, wenn ein Bitmuster für Windows 7-Taskleiste Registerkarte Miniaturansicht der untergeordneten MDI-Fensters gestreckt werden muss.|  
|[CMDIChildWndEx::OnUpdateFrameTitle](#onupdateframetitle)|Vom Framework aufgerufen wird zum Aktualisieren des Frame-Titels. (Überschreibt `CMDIChildWnd::OnUpdateFrameTitle`.)|  
|[CMDIChildWndEx::PaneFromPoint](#panefrompoint)|Gibt den Bereich, der den angegebenen Punkt enthält.|  
|`CMDIChildWndEx::PreTranslateMessage`|Von der Klasse verwendet [CWinApp](../../mfc/reference/cwinapp-class.md) auf fenstermeldungen zu übersetzen, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMDIChildWndEx::RecalcLayout](#recalclayout)|Berechnet das Layout des Fensters.|  
|[CMDIChildWndEx::RegisterTaskbarTab](#registertaskbartab)|Windows 7-Taskleiste Registerkarten registriert untergeordneten MDI-Fensters.|  
|[CMDIChildWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|Entfernt einen Bereich von der Dockingstation-Manager.|  
|[CMDIChildWndEx::SetRelatedTabGroup](#setrelatedtabgroup)||  
|[CMDIChildWndEx::SetTaskbarTabActive](#settaskbartabactive)|Aktiviert die entsprechende Registerkarte der Windows 7-Taskleiste.|  
|[CMDIChildWndEx::SetTaskbarTabOrder](#settaskbartaborder)|Fügt ein untergeordnetes MDI-Objekt vor dem angegebenen Fenster auf Windows 7-Taskleiste Registerkarten.|  
|[CMDIChildWndEx::SetTaskbarTabProperties](#settaskbartabproperties)|Legt Eigenschaften für eine Registerkarte der Windows 7-Taskleiste fest.|  
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](#settaskbarthumbnailcliprect)|Intern vom Framework aufgerufen wird Auswahlrechteck, wählen Sie einen Teil des Clientbereichs des Fensters Miniaturansicht in der Taskleiste anzeigen eines Fensters fest.|  
|[CMDIChildWndEx::ShowPane](#showpane)||  
|[CMDIChildWndEx::UnregisterTaskbarTab](#unregistertaskbartab)|Entfernt untergeordnete MDI-Element von Windows 7-Taskleiste Registerkarten.|  
|[CMDIChildWndEx::UpdateTaskbarTabIcon](#updatetaskbartabicon)|Windows 7-Taskleiste Registerkartensymbol wird aktualisiert.|  
  
## <a name="remarks"></a>Hinweise  
 Um erweiterte andockbaren Features im MDI-Anwendung nutzen zu können, leiten Sie die MDI-untergeordneten Fenster-Klasse der Anwendung `CMDIChildWndEx` anstelle von [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine Klasse von abgeleitet `CMDIChildWndEx`. Dieser Codeausschnitt stammt aus der [VisualStudioDemo-Beispiel: MFC-Anwendung für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&3;](../../mfc/codesnippet/cpp/cmdichildwndex-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
 `TRUE`So fügen im Bereich am Ende der Liste der Bereiche für den docking-Manager; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`im Bereich mit den docking-Manager; erfolgreich registriert wurde andernfalls `FALSE`.  
  
##  <a name="addtabbedpane"></a>CMDIChildWndEx::AddTabbedPane  
 Fügt ein Fenster mit Registerkarten.  
  
```  
void AddTabbedPane(CDockablePane* pControlBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 Ein Zeiger auf den Bereich.  
  
##  <a name="adjustdockinglayout"></a>CMDIChildWndEx::AdjustDockingLayout  
 Passt die andocklayout an.  
  
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
 `TRUE`Wenn das Fenster in angezeigt werden kann der **Windows** (Dialogfeld), andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode in einer abgeleiteten Klasse überschreiben und zurückgeben `FALSE` , wenn das Fenster nicht soll, können Sie in angezeigt werden der **Windows** im Dialogfeld. Diese Funktion wird aufgerufen, von `CMFCWindowsManagerDialog`.  
  
##  <a name="dockpane"></a>CMDIChildWndEx::DockPane  
 Wird einen Bereich angedockt.  
  
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
 Diese Methode verwendet den angegebenen Bereich `pBar` und wird es an der linken Seite des angegebenen Bereichs `pLeftOf`.  
  
 Rufen Sie diese Methode, wenn Sie mehrere Bereiche in einer vordefinierten Reihenfolge andocken möchten.  
  
##  <a name="enableautohidepanes"></a>CMDIChildWndEx::EnableAutoHidePanes  
 Ermöglicht das automatische Ausblenden Modus für Bereiche, wenn diese an den angegebenen Seiten des Fensters angedockt sind.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwDockStyle`  
 Gibt die Seiten für das Hauptrahmenfenster, das aktiviert ist. Verwenden Sie eine oder mehrere der folgenden Flags.  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist. andernfalls `FALSE`.  
  
##  <a name="enabledocking"></a>CMDIChildWndEx::EnableDocking  
 Ermöglicht das Andocken des untergeordneten Fensters Hauptframe.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwDockStyle`  
 Gibt die Dockingstation Ausrichtung zu aktivieren.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Andocken Ausrichtung an den Hauptframe aktivieren. Sie können eine Kombination von Flags CBRS_ALIGN_ übergeben (Weitere Informationen finden Sie unter [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
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
 Ist ein Dokument, das die untergeordneten MDI-Fensters angezeigt. Im Allgemeinen zeigt das Fenster Daten, die aus geladenen oder in einer Datei gespeichert. Daher ist der Name des Dokuments, den Namen der Datei. Die standardmäßige Implementierung des `GetDocumentName` gibt eine Zeichenfolge, die entnommen `CDocument::GetPathName`.  
  
 Wenn das Fenster ein Dokument, die nicht aus einer Datei geladen wird öffnet, diese Methode in einer abgeleiteten Klasse überschreiben und eine eindeutige Dokument-ID zurück.  
  
 `GetDocumentName`wird vom Framework aufgerufen, wenn den Status aller geöffneten Dokumente gespeichert. Die zurückgegebene Zeichenfolge wird in die Registrierung geschrieben.  
  
 Wenn Sie das Framework Status später wiederherstellen, wird der Name des Dokuments aus der Registrierung gelesen und an [CMDIFrameWndEx::CreateDocumentWindow](../../mfc/reference/cmdiframewndex-class.md#createdocumentwindow). Überschreiben Sie diese Methode in einer [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)-abgeleitete Klasse, und erstellen oder öffnen Sie ein Dokument mit diesem Namen und in der Datei mit diesem Namen zu lesen. Wenn das Dokument nicht auf eine Datei ist, erstellen Sie das Dokument anhand der Dokument-ID selbst. Sie sollten die vorangegangenen Aktionen ausführen, nur, wenn Sie beabsichtigen, speichern und Wiederherstellen von Dokumenten.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der `GetDocumentName`-Methode gezeigt. Dieser Codeausschnitt stammt aus der [VisualStudioDemo-Beispiel: MFC-Anwendung für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&17;](../../mfc/codesnippet/cpp/cmdichildwndex-class_2.cpp)]  
  
##  <a name="getframeicon"></a>CMDIChildWndEx::GetFrameIcon  
 Aufgerufen, um das Symbol der untergeordneten MDI-Fensters abzurufen.  
  
```  
virtual HICON GetFrameIcon() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das Fenstersymbol.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework, um zu ermitteln welcher Symbol auf der MDI-Registerkarte angezeigt, die die untergeordneten MDI-Rahmenfenster enthält.  
  
 Standardmäßig gibt diese Methode das Fenstersymbol. Überschreiben Sie `GetFrameIcon` in einen `CMDIChildWndEx`-abgeleitete Klasse, um dieses Verhalten anzupassen.  
  
##  <a name="getframetext"></a>CMDIChildWndEx::GetFrameText  
 Aufgerufen, um den Text für die untergeordneten MDI-Fensters abzurufen.  
  
```  
virtual CString GetFrameText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Frame Fenstertext enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework, um zu bestimmen, die auf die MDI-Registerkarte angezeigt, die die untergeordneten MDI-Rahmenfenster enthält Text.  
  
 Standardmäßig gibt diese Methode den Text aus. Überschreiben Sie `GetFrameText` in einen `CMDIChildWndEx`-abgeleitete Klasse, um dieses Verhalten anzupassen.  
  
##  <a name="getpane"></a>CMDIChildWndEx::GetPane  
 Sucht einen Bereich von der angegebenen Steuerelement-ID  
  
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
 Gibt ein Zeiger auf einen andockbaren Bereich, die Teil einer Gruppe der MDI-Dokumente im Registerkartenformat.  
  
```  
CDockablePane* GetTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf einen andockbaren Bereich, die Teil einer Gruppe von MDI werden Dokumente im Registerkartenformat.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>CMDIChildWndEx::GetToolbarButtonToolTipText  
 Aufgerufen, um eine QuickInfo für eine Symbolleisten-Schaltfläche abzurufen.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton*, 
    CString&);
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die QuickInfo angezeigt wird. Die Standardimplementierung gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie benutzerdefinierte QuickInfos für Symbolleisten-Schaltflächen angezeigt werden soll.  
  
##  <a name="insertpane"></a>CMDIChildWndEx::InsertPane  
 Registriert den angegebenen Bereich der docking-Manager.  
  
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
 Wenn `TRUE`, `pControlBar` eingefügt wird, nachdem `pTarget`. Wenn `FALSE`, `pControlBar` wird eingefügt, bevor Sie `pTarget`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist, `FALSE` andernfalls.  
  
##  <a name="ispointneardocksite"></a>CMDIChildWndEx::IsPointNearDockSite  
 Bestimmt, ob es sich bei ein angegebenen Punkt in der Nähe der Dock-Website ist.  
  
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
 Gibt an, welchen Rand in der Nähe der Punkt ist. Mögliche Werte sind `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, und`CBRS_ALIGN_BOTTOM`  
  
 [in] `bOuterEdge`  
 `TRUE`Wenn der Punkt in der Nähe von den äußeren Rahmen des Standorts Dock ist; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Punkt in der Nähe der Dock-Website ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Punkt ist in der Nähe der docksite, wenn es innerhalb der Vertraulichkeit in der Dockingstation Manager festgelegt ist. Die Vertraulichkeit der Standardwert beträgt 15 Pixel.  
  
##  <a name="isreadonly"></a>CMDIChildWndEx::IsReadOnly  
 Gibt an, ob das Dokument im untergeordneten Fenster angezeigt wird, schreibgeschützt ist.  
  
```  
virtual BOOL IsReadOnly();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Dokument schreibgeschützt ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird verwendet, um zu verhindern, dass der schreibgeschützte Dokumente speichern.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Überschreiben der `IsReadOnly` Methode. Dieser Codeausschnitt stammt aus der [VisualStudioDemo-Beispiel: MFC-Anwendung für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#2;](../../mfc/codesnippet/cpp/cmdichildwndex-class_3.cpp)]  
  
##  <a name="istabbedpane"></a>CMDIChildWndEx::IsTabbedPane  
 Gibt an, ob die untergeordneten MDI-Fensters einen andockbaren Bereich enthält.  
  
```  
BOOL IsTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die untergeordneten MDI-Fensters einen andockbaren Bereich, der in ein Dokument im Registerkartenformat konvertiert wurde enthält. andernfalls `FALSE`.  
  
##  <a name="onmoveminiframe"></a>CMDIChildWndEx::OnMoveMiniFrame  
 Aufgerufen, um ein Minirahmenfenster zu verschieben.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFrame`  
 Ein Zeiger auf ein Minirahmenfenster.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich, andernfalls ist `FALSE`.  
  
##  <a name="onsetpreviewmode"></a>CMDIChildWndEx::OnSetPreviewMode  
 Vom Framework aufgerufen wird, starten oder Beenden der Seitenansicht angezeigt.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bPreview`  
 Wenn `TRUE`, geben Sie die Seitenansicht. Wenn `FALSE`, Seitenansicht beenden.  
  
 [in] `pState`  
 Ein Zeiger auf die Struktur der Seitenansicht Zustand.  
  
##  <a name="onupdateframetitle"></a>CMDIChildWndEx::OnUpdateFrameTitle  
 Vom Framework aufgerufen wird zum Aktualisieren des Frame-Titels.  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAddToTitle`  
 Wenn `TRUE`, fügen Sie den Namen des Dokuments auf den Titel.  
  
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
 Erhöhen Sie den Suchbereich, um diesen Betrag. Ein Bereich erfüllt die Suchkriterien, fällt der angegebene Punkt im Bereich erhöhte.  
  
 [in] `bExactBar`  
 `TRUE`ignoriert die `nSensitivity` Parameter ist, andernfalls `FALSE`.  
  
 [in] `pRTCBarType`  
 Wenn dies nicht `NULL`, die-Methode sucht nur die Bereiche des angegebenen Typs.  
  
 [in] `dwAlignment`  
 Wenn ein Bereich am angegebenen Punkt gefunden wird, enthält dieser Parameter den Rand des Bereichs, der dem angegebenen Punkt am nächsten ist. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CBasePane`-abgeleitetes Objekt mit dem angegebenen Punkt oder `NULL` Wenn kein Bereich gefunden wurde.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zu bestimmen, ob ein Bereich mit den angegebenen Punkt gemäß den angegebenen Bedingungen wie z. B. die Common Language Runtime-Klasse und Sichtbarkeit enthält.  
  
 Wenn die Funktion zurückgibt und ein Bereich gefunden wurde, `dwAlignment` die Ausrichtung des angegebenen Punkt enthält. Wenn der Punkt am nächsten am Anfang des Bereichs befand sich z. B. `dwAlignment` Wert `CBRS_ALIGN_TOP`.  
  
##  <a name="recalclayout"></a>CMDIChildWndEx::RecalcLayout  
 Berechnet das Layout des Fensters.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bNotify`  
 Wenn `TRUE`, das aktive in-Place-Element für das Fenster empfängt eine Benachrichtigung über das Layout ändern.  
  
##  <a name="removepanefromdockmanager"></a>CMDIChildWndEx::RemovePaneFromDockManager  
 Entfernt einen Bereich von der Dockingstation-Manager.  
  
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
 Wenn `TRUE`, passen Sie das Andocken Layout sofort.  
  
 [in] `bAutoHide`  
 Wenn `TRUE`, die andocklayout bezieht sich auf die Liste der Balken automatisch im Hintergrund. Wenn `FALSE`, die andocklayout bezieht sich auf die Liste der regulären Bereiche.  
  
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
 Aktualisiert das Windows 7-Taskleiste Registerkartensymbol.  
  
```  
virtual void UpdateTaskbarTabIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 `hIcon`  
 Ein Handle für ein Symbol auf der Registerkarte der Windows 7-Taskleiste angezeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="unregistertaskbartab"></a>CMDIChildWndEx::UnregisterTaskbarTab  
 Entfernt das untergeordnete MDI-Element von Windows 7-Taskleiste Registerkarten.  
  
```  
void UnregisterTaskbarTab(BOOL bCheckRegisteredMDIChildCount = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bCheckRegisteredMDIChildCount`  
 Gibt an, ob diese Funktion die Anzahl der untergeordneten MDI-Objekte registriert MDI-Registerkarten zu überprüfen muss. Wenn dieser Wert 0 ist, entfernt diese Funktion das Clippingrechteck aus Taskleiste-Miniaturansicht der Anwendung.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settaskbarthumbnailcliprect"></a>CMDIChildWndEx::SetTaskbarThumbnailClipRect  
 Aufgerufen, das Clippingrechteck an, wählen Sie einen Teil des Clientbereichs des Fensters Miniaturansicht in der Taskleiste anzeigen eines Fensters fest.  
  
```  
virtual BOOL SetTaskbarThumbnailClipRect(CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Gibt das neue Auswahlrechteck. Wenn das Rechteck leer oder null ist, wird das Clipping entfernt.  
  
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
 Fügt der untergeordneten MDI-Fensters, bevor das angegebene Fenster auf Windows 7-Taskleiste Registerkarten.  
  
```  
void SetTaskbarTabOrder(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndBefore`  
 Ein Zeiger auf, für deren Miniaturansicht, auf der linken Seite eingefügt wird, untergeordneten MDI-Fensters. In diesem Fenster muss bereits registriert sein, über `RegisterTaskbarTab`. Wenn dieser Wert ist `NULL`, die neue Miniaturansicht wird am Ende der Liste hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settaskbartabactive"></a>CMDIChildWndEx::SetTaskbarTabActive  
 Aktiviert die entsprechende Registerkarte für die Windows 7-Taskleiste.  
  
```  
void SetTaskbarTabActive();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="registertaskbartab"></a>CMDIChildWndEx::RegisterTaskbarTab  
 Windows 7-Taskleiste Registerkarten registriert untergeordneten MDI-Fensters.  
  
```  
virtual void RegisterTaskbarTab(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndBefore`  
 Ein Zeiger auf, für deren Miniaturansicht, auf der linken Seite eingefügt wird, untergeordneten MDI-Fensters. In diesem Fenster muss bereits registriert sein, über `RegisterTaskbarTab`. Wenn dieser Wert ist `NULL`, die neue Miniaturansicht wird am Ende der Liste hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ontaskbartabthumbnailstretch"></a>CMDIChildWndEx::OnTaskbarTabThumbnailStretch  
 Vom Framework aufgerufen, wenn eine Bitmap für Windows 7-Taskleiste Registerkarte Miniaturansicht der untergeordneten MDI-Fensters gestreckt werden muss.  
  
```  
virtual BOOL OnTaskbarTabThumbnailStretch(
    HBITMAP hBmpDst,  
    const CRect& rectDst,  
    HBITMAP hBmpSrc,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `hBmpDst`  
 Ein Handle für ein Ziel-Bitmap.  
  
 `rectDst`  
 Gibt das Zielrechteck.  
  
 `hBmpSrc`  
 Ein Handle für eine Quellbitmap.  
  
 `rectSrc`  
 Gibt das Rechteck.  
  
### <a name="remarks"></a>Hinweise  
 Requirementher oder ihm ihm ihm er ihn ihm ihm **:** afxmdichildwndex.h  
  
##  <a name="ontaskbartabthumbnailmouseactivate"></a>CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate  
 Wird vom Framework aufgerufen, wenn die Taskleiste Registerkarte Miniaturansicht WM_MOUSEACTIVATE Nachricht verarbeiten soll.  
  
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
 Gibt die Ortskennzahl Treffertest. Treffertests ist ein Test, der die Position des Cursors bestimmt.  
  
 `message`  
 Gibt die Anzahl der Maus-Nachricht.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung aktiviert die zugehörigen untergeordneten MDI-Rahmens.  
  
##  <a name="ontaskbartabthumbnailactivate"></a>CMDIChildWndEx::OnTaskbarTabThumbnailActivate  
 Wird vom Framework aufgerufen, wenn die Taskleiste Registerkarte Miniaturansicht WM_ACTIVATE Nachricht verarbeiten soll.  
  
```  
virtual void OnTaskbarTabThumbnailActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>Parameter  
 `nState`  
 Gibt an, ob die `CWnd` aktiviert oder deaktiviert ist.  
  
 `pWndOther`  
 Zeiger auf die `CWnd` aktiviert oder deaktiviert. Der Zeiger kann `NULL`, und es kann temporär sein.  
  
 `bMinimized`  
 Gibt den minimierten Zustand der `CWnd` aktiviert oder deaktiviert. Der Wert `TRUE` gibt an, das Fenster wird minimiert.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung aktiviert die zugehörigen untergeordneten MDI-Rahmens.  
  
##  <a name="onpresstaskbarthmbnailclosebutton"></a>CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton  
 Vom Framework aufgerufen, wenn der Benutzer die Schaltfläche "Schließen" auf die Registerkarte Taskleiste drückt.  
  
```  
virtual void OnPressTaskbarThmbnailCloseButton();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ongeticonicthumbnail"></a>CMDIChildWndEx::OnGetIconicThumbnail  
 Vom Framework aufgerufen, wenn eine Bitmap für die iconic Miniaturansicht des untergeordneten MDI-Fensters abgerufen werden muss.  
  
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
 Vom Framework aufgerufen, wenn eine Bitmap für die live-Vorschau der untergeordneten MDI-Fensters abgerufen werden muss.  
  
```  
virtual HBITMAP OnGetIconicLivePreviewBitmap(
    BOOL bIsMDIChildActive,  
    CPoint& ptLocation);
```  
  
### <a name="parameters"></a>Parameter  
 `bIsMDIChildActive`  
 Dieser Parameter ist `TRUE` , wenn die Bitmap für die untergeordneten MDI-Fensters angefordert wird, die derzeit aktiv ist und das Hauptfenster wird nicht minimiert. Die Standardeinstellung in diesem Fall nimmt eine Momentaufnahme des Hauptfensters.  
  
 `ptLocation`  
 Gibt den Speicherort der Bitmap in der Main (oberste Ebene) Fenster Clientkoordinaten. Dieser Punkt muss vom aufgerufenen bereitgestellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn verarbeitet, gibt ein Handle für eine gültige 32-bpp-Bitmap, andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode in einer abgeleiteten Klasse überschreiben, und geben Sie eine gültige 32 bpp Bitmap für die live-Vorschau der untergeordneten MDI-Fensters zurück. Diese Methode wird aufgerufen, nur bei untergeordneten MDI-Fensters auf Registerkarten für Windows 7-Taskleiste angezeigt wird. Wenn Sie zurückkehren, `NULL`, MFC ruft die Standardhandler und ruft mithilfe von Bitmaps `PrintClient` oder `PrintWindow`.  
  
##  <a name="m_dwdefaulttaskbartabpropertyflags"></a>CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags  
 Eine Kombination von Flags, die durch das Framework übergeben wird die `SetTaskbarTabProperties` Methode, wenn eine Registerkarte (MDI-untergeordnet) mit Windows 7-Taskleiste Registerkarten registriert wird.  
  
```  
AFX_IMPORT_DATA static DWORD m_dwDefaultTaskbarTabPropertyFlags;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Standardkombination ist STPF_USEAPPTHUMBNAILWHENACTIVE | STPF_USEAPPPEEKWHENACTIVE.  
  
##  <a name="istaskbarthumbnailcliprectenabled"></a>CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled  
 Erfahren Sie, ob die automatische Auswahl eines Teils des Clientbereichs des Fensters Miniaturansicht in der Taskleiste anzeigen eines Fensters aktiviert oder deaktiviert ist.  
  
```  
BOOL IsTaskbarThumbnailClipRectEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` , wenn die automatische Auswahl von einen Teil des Clientbereichs zum Anzeigen eines Fensters aktiviert, andernfalls ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="istaskbartabssupportenabled"></a>CMDIChildWndEx::IsTaskbarTabsSupportEnabled  
 Erfahren Sie, ob die untergeordneten MDI-Fensters auf Windows 7-Taskleiste Registerkarten angezeigt werden kann.  
  
```  
BOOL IsTaskbarTabsSupportEnabled();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die untergeordneten MDI-Fensters auf Windows 7-Taskleiste Registerkarten angezeigt werden kann; `FALSE` Wenn untergeordneten MDI-Fensters nicht auf Windows 7-Taskleiste Registerkarten angezeigt werden kann.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isregisteredwithtaskbartabs"></a>CMDIChildWndEx::IsRegisteredWithTaskbarTabs  
 Gibt `TRUE` untergeordneten MDI-Fensters mit Windows 7-Taskleiste Registerkarten erfolgreich registriert wurde.  
  
```  
BOOL IsRegisteredWithTaskbarTabs();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die untergeordneten MDI-Fensters mit Registerkarten für Windows 7-Taskleiste; registriert ist andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="invalidateiconicbitmaps"></a>CMDIChildWndEx::InvalidateIconicBitmaps  
 Erklärt eine iconic Bitmapdarstellung eines untergeordneten MDI-Elements.  
  
```  
BOOL InvalidateIconicBitmaps();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `FALSE` wenn Unterstützung für Windows 7-Taskleiste deaktiviert ist oder das untergeordnete MDI-Element nicht, mit Registerkarten für Windows 7-Taskleiste registriert ist; andernfalls `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Sollte aufgerufen werden, wenn die live-Inhalten oder die Größe eines untergeordneten MDI-Elements geändert hat.  
  
##  <a name="gettaskbarthumbnailcliprect"></a>CMDIChildWndEx::GetTaskbarThumbnailClipRect  
 Vom Framework aufgerufen, wenn einen Teil des Clientbereichs des Fensters Miniaturansicht in der Taskleiste anzeigen eines Fensters aktivieren muss.  
  
```  
virtual CRect GetTaskbarThumbnailClipRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Rechteck in Windows-Koordinaten. Dieses Rechteck wird auf den Clientbereich des Rahmens auf oberster Ebene zugeordnet. Das Rechteck darf, deaktivieren Sie das Auswahlrechteck leer sein.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettaskbarpreviewwnd"></a>CMDIChildWndEx::GetTaskbarPreviewWnd  
 Vom Framework aufgerufen, wenn ein untergeordnetes Fenster (in der Regel ein Fenster anzeigen oder den Splitter) auf die Registerkarte Miniaturansicht eines Windows 7-Taskleiste angezeigt werden abgerufen werden muss.  
  
```  
virtual CWnd* GetTaskbarPreviewWnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen gültigen Zeiger auf zurückgeben sollte ein `CWnd` Objekt, dessen Vorschau soll, auf die Registerkarte für eine Windows 7-Taskleiste angezeigt werden im Zusammenhang mit diesem untergeordneten MDI-Fensters. Die standardmäßige Implementierung gibt als untergeordnetes Fenster von diesem untergeordnete MDI-Element mit AFX_IDW_PANE_FIRST Steuerelement-ID (ist in der Regel eine `CView`-Klasse).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettabproxywnd"></a>CMDIChildWndEx::GetTabProxyWnd  
 Gibt die Registerkarte Proxy-Fenster mit Registerkarten für Windows 7-Taskleiste registriert.  
  
```  
CMDITabProxyWnd* GetTabProxyWnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein `CMDITabProxyWnd` -Objekt, das mit Windows 7-Taskleiste Registerkarten registriert ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabletaskbarthumbnailcliprect"></a>CMDIChildWndEx::EnableTaskbarThumbnailClipRect  
 Aktiviert oder deaktiviert die automatische Auswahl von einen Teil des Clientbereichs des Fensters Miniaturansicht in der Taskleiste anzeigen eines Fensters.  
  
```  
void EnableTaskbarThumbnailClipRect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob ( `TRUE`), oder deaktivieren ( `FALSE`) automatische Auswahl eines Teils des Clientbereichs des Fensters, angezeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="canshowontaskbartabs"></a>CMDIChildWndEx::CanShowOnTaskBarTabs  
 Teilt dem Framework mit, ob dieser untergeordneten MDI-Fensters auf Windows 7-Taskleiste Registerkarten angezeigt werden kann.  
  
```  
virtual BOOL CanShowOnTaskBarTabs();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Inhalt des untergeordneten MDI-Fensters auf Windows 7-Taskleistenminiaturansichten angezeigt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode in einer abgeleiteten Klasse überschreiben und zurückgeben `FALSE` , die Darstellung dieser untergeordneten MDI-auf Windows 7-Taskleiste Registerkarten deaktivieren.  
  
##  <a name="activatetoplevelframe"></a>CMDIChildWndEx::ActivateTopLevelFrame  
 Vom Framework aufgerufen Fenster auf oberster Ebene zu aktivieren, wenn die Anwendung über eine Registerkarte Taskleiste aktiviert ist.  
  
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

