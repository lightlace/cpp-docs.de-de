---
title: Klasse CFrameWndEx | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFrameWndEx
dev_langs:
- C++
helpviewer_keywords:
- CFrameWndEx class
ms.assetid: 5830aca8-4a21-4f31-91f1-dd5477ffcc8d
caps.latest.revision: 39
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b2106c3067a0164395eddab0e8b156728697d5bb
ms.lasthandoff: 02/24/2017

---
# <a name="cframewndex-class"></a>CFrameWndEx-Klasse
Implementiert die Funktionalität eines Windows-SDI-Rahmenfensters (Single Document Interface), wobei es sich um ein überlappendes oder ein Popupfenster handeln kann. Ebenfalls bereitgestellt werden Member zum Verwalten des Fensters. Es erweitert die [CFrameWnd](../../mfc/reference/cframewnd-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFrameWndEx::ActiveItemRecalcLayout](#activeitemrecalclayout)|Passt das Layout der OLE-Clientelement und den Rand des Clientbereichs.|  
|`CFrameWndEx::AddDockSite`|Diese Methode wird nicht verwendet.|  
|[CFrameWndEx::AddPane](#addpane)|Registriert eine Steuerleiste docking-Manager.|  
|[CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)|Berechnet das Layout für alle Bereiche, die an das Rahmenfenster angedockt sind.|  
|[CFrameWndEx::DelayUpdateFrameMenu](#delayupdateframemenu)|Legt die Frame-Menü und dann aktualisiert, wenn befehlsverarbeitung im Leerlauf befindet.|  
|[CFrameWndEx::DockPane](#dockpane)|Das Rahmenfenster im angegebenen Bereich angedockt.|  
|[CFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.|  
|[CFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)|Können den Modus "automatisch im Hintergrund" für die Bereiche, wenn diese an den angegebenen Seiten des Hauptrahmenfenster angedockt sind.|  
|[CFrameWndEx::EnableDocking](#enabledocking)|Ermöglicht das Andocken der Bereiche, die an das Rahmenfenster gehören.|  
|[CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)|Anzeigen oder ausblenden im Hauptmenü in einem Vollbild-Modus.|  
|[CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode)|Ermöglicht den Vollbildmodus für das Rahmenfenster.|  
|[CFrameWndEx::EnableLoadDockState](#enableloaddockstate)|Aktiviert oder deaktiviert das Laden der Andockstatus.|  
|[CFrameWndEx::EnablePaneMenu](#enablepanemenu)|Aktiviert oder deaktiviert die automatische Behandlung von klicken Sie im Bereich.|  
|[CFrameWndEx::GetActivePopup](#getactivepopup)|Gibt einen Zeiger auf den momentan angezeigten Popupmenü.|  
|[CFrameWndEx::GetDefaultResId](#getdefaultresid)|Gibt die Ressourcen-ID, die Sie angegeben, wenn das Framework das Rahmenfenster geladen.|  
|[CFrameWndEx::GetDockingManager](#getdockingmanager)|Ruft die [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) Objekt für das Rahmenfenster.|  
|[CFrameWndEx::GetMenuBar](#getmenubar)|Gibt einen Zeiger auf das Menüleistenobjekt zurück, das an das Rahmenfenster angefügt ist.|  
|[CFrameWndEx::GetPane](#getpane)|Gibt einen Zeiger auf den Bereich, der die angegebene ID verfügt.|  
|[CFrameWndEx::GetRibbonBar](#getribbonbar)|Ruft die Menüband-Steuerelement für den Rahmen.|  
|[CFrameWndEx::GetTearOffBars](#gettearoffbars)|Gibt eine Liste von Bereichsobjekten zurück, die sich in einem abtrennbaren Zustand befinden.|  
|[CFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Vom Framework aufgerufen, wenn die Anwendung die QuickInfo für eine Symbolleisten-Schaltfläche angezeigt wird.|  
|[CFrameWndEx::InsertPane](#insertpane)|Registriert einen Bereich mit dem docking-Manager.|  
|[CFrameWndEx::IsFullScreen](#isfullscreen)|Bestimmt, ob das Rahmenfenster im Vollbildmodus ausgeführt wird.|  
|[CFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|Bestimmt, ob der Zeiger auf das Menü Bar-Objekt gültig ist.|  
|[CFrameWndEx::IsPointNearDockSite](#ispointneardocksite)|Gibt an, ob der Punkt in einer Zone Ausrichtung befindet.|  
|[CFrameWndEx::IsPrintPreview](#isprintpreview)|Gibt an, ob das Rahmenfenster im Seitenansichtsmodus ist.|  
|[CFrameWndEx::LoadFrame](#loadframe)|Diese Methode wird aufgerufen, nachdem Konstruktion Rahmenfenster erstellen und Laden ihre Ressourcen.|  
|[CFrameWndEx::NegotiateBorderSpace](#negotiateborderspace)|Implementiert OLE-Client Rahmen aushandeln.|  
|[CFrameWndEx::OnActivate](#onactivate)|Das Framework ruft diese Methode auf, wenn Benutzereingaben zu oder von der Frame gewechselt wird.|  
|[CFrameWndEx::OnActivateApp](#onactivateapp)|Wird vom Framework aufgerufen, wenn die Anwendung aktiviert oder deaktiviert ist.|  
|[CFrameWndEx::OnChangeVisualManager](#onchangevisualmanager)|Wird vom Framework aufgerufen, wenn eine Änderung des Frames, eine Änderung an der visuellen Manager erfordert.|  
|[CFrameWndEx::OnClose](#onclose)|Das Framework ruft diese Methode, um den Rahmen zu schließen.|  
|[CFrameWndEx::OnCloseDockingPane](#onclosedockingpane)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **schließen** auf einen andockbaren Bereich auf die Schaltfläche.|  
|[CFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **schließen** Schaltfläche auf einem schwebenden Mini-Rahmenfenster.|  
|[CFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|Wird vom Framework aufgerufen, wenn ein aktives Popupmenü eine WM_DESTROY-Meldung verarbeitet.|  
|[CFrameWndEx::OnCmdMsg](#oncmdmsg)|Sendet Nachrichten-Befehl.|  
|[CFrameWndEx::OnContextHelp](#oncontexthelp)|Aufgerufen, Hilfe, um Kontext angezeigt verknüpft.|  
|[CFrameWndEx::OnCreate](#oncreate)|Wird vom Framework aufgerufen, nachdem der Rahmen erstellt wurde.|  
|[CFrameWndEx::OnDestroy](#ondestroy)|Wird vom Framework aufgerufen, wenn der Frame zerstört wird.|  
|[CFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|Wird vom Framework aufgerufen, wenn die Anwendung das ein Menüelement zugeordnete Bild zeichnet.|  
|[CFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|Vom Framework aufgerufen wird bei einer `CMFCPopupMenu` -Objekt Prozesse eine [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Nachricht.|  
|[CFrameWndEx::OnDWMCompositionChanged](#ondwmcompositionchanged)|Wird vom Framework aufgerufen, wenn Desktop Window Manager (DWM) Komposition aktiviert oder deaktiviert wurde.|  
|[CFrameWndEx::OnExitSizeMove](#onexitsizemove)|Vom Framework aufgerufen, wenn der Frame beendet wird, verschieben oder dessen Größe ändern.|  
|[CFrameWndEx::OnGetMinMaxInfo](#ongetminmaxinfo)|Wird vom Framework aufgerufen, wenn Frames Größe an Fenster Dimension begrenzen.|  
|[CFrameWndEx::OnIdleUpdateCmdUI](#onidleupdatecmdui)|Vom Framework aufgerufen, die die Frame-Anzeige zu aktualisieren, wenn befehlsverarbeitung im Leerlauf befindet.|  
|[CFrameWndEx::OnLButtonDown](#onlbuttondown)|Das Framework ruft diese Methode auf, wenn der Benutzer die linke Maustaste drückt.|  
|[CFrameWndEx::OnLButtonUp](#onlbuttonup)|Das Framework ruft diese Methode auf, wenn der Benutzer die linke Maustaste loslässt.|  
|[CFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|Vom Framework aufgerufen wird bei einer `CMFCToolBarButton` -Objekt Prozesse eine `WM_NCHITTEST` Nachricht.|  
|[CFrameWndEx::OnMenuChar](#onmenuchar)|Vom Framework aufgerufen, wenn ein Menü angezeigt wird und der Benutzer drückt einen Schlüssel, der nicht an einen Befehl.|  
|[CFrameWndEx::OnMouseMove](#onmousemove)|Das Framework ruft diese Methode auf, wenn der Mauszeiger bewegt wird.|  
|[CFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)|Vom Framework aufgerufen, wenn ein Fenster verschoben wird.|  
|[CFrameWndEx::OnNcActivate](#onncactivate)|Wird vom Framework aufgerufen, wenn der nicht-Clientbereich des Rahmens neu gezeichnet werden muss, um eine Änderung im aktiven Zustand anzuzeigen.|  
|[CFrameWndEx::OnNcCalcSize](#onnccalcsize)|Wird vom Framework aufgerufen, wenn die Größe und Position des Clientbereichs berechnet werden müssen.|  
|[CFrameWndEx::OnNcHitTest](#onnchittest)|Wird vom Framework aufgerufen, wenn der Mauszeiger bewegt wird, oder wenn eine Maustaste gedrückt oder losgelassen wird.|  
|[CFrameWndEx::OnNcMouseMove](#onncmousemove)|Wird vom Framework aufgerufen, wenn der Mauszeiger in einem nicht-Clientbereich.|  
|[CFrameWndEx::OnNcPaint](#onncpaint)|Wird vom Framework aufgerufen, wenn der nicht-Clientbereich gezeichnet werden muss.|  
|[CFrameWndEx::OnPaneCheck](#onpanecheck)|Aufgerufen, um die Sichtbarkeit eines Bereichs zu steuern.|  
|[CFrameWndEx::OnPostPreviewFrame](#onpostpreviewframe)|Wird vom Framework aufgerufen, wenn der Benutzer den Seitenansichtmodus geändert hat.|  
|[CFrameWndEx::OnPowerBroadcast](#onpowerbroadcast)|Vom Framework aufgerufen, wenn ein Power Management-Ereignis eintritt.|  
|[CFrameWndEx::OnSetMenu](#onsetmenu)|Vom Framework aufgerufen wird im Menü Fenster Frame zu ersetzen.|  
|[CFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|Vom Framework aufgerufen wird zum Festlegen des Modus "Seitenansicht" für den Frame.|  
|[CFrameWndEx::OnSetText](#onsettext)|Aufgerufen, um den Text eines Fensters festzulegen.|  
|[CFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)|Vom Framework aufgerufen, wenn eine schnelle anpassen Bereich aktiviert ist.|  
|[CFrameWndEx::OnShowPanes](#onshowpanes)|Vom Framework aufgerufen wird, anzeigen oder Ausblenden von Bereichen.|  
|[CFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|Wird vom Framework aufgerufen, wenn ein Popup-Menü aktiviert ist.|  
|[CFrameWndEx::OnSize](#onsize)|Das Framework ruft diese Methode nach der Frame ändert.|  
|[CFrameWndEx::OnSizing](#onsizing)|Das Framework ruft diese Methode auf, wenn der Benutzer den Frame ändert.|  
|[CFrameWndEx::OnSysColorChange](#onsyscolorchange)|Vom Framework aufgerufen, wenn sich die Systemfarben ändern.|  
|[CFrameWndEx::OnTearOffMenu](#ontearoffmenu)|Wird vom Framework aufgerufen, wenn ein Menü mit einer Leiste abtrennbare aktiviert ist.|  
|[CFrameWndEx::OnToolbarContextMenu](#ontoolbarcontextmenu)|Aufgerufen, um ein Kontextmenü Symbolleiste zu erstellen.|  
|[CFrameWndEx::OnToolbarCreateNew](#ontoolbarcreatenew)|Das Framework ruft diese Methode, um eine neue Symbolleiste zu erstellen.|  
|[CFrameWndEx::OnToolbarDelete](#ontoolbardelete)|Wird vom Framework aufgerufen, wenn eine Symbolleiste gelöscht wird.|  
|[CFrameWndEx::OnUpdateFrameMenu](#onupdateframemenu)|Aufgerufen, klicken Sie im Frame fest.|  
|[CFrameWndEx::OnUpdateFrameTitle](#onupdateframetitle)|Das Framework ruft diese Methode, um die Titelleiste des Rahmenfensters.|  
|[CFrameWndEx::OnUpdatePaneMenu](#onupdatepanemenu)|Vom Framework aufgerufen wird, klicken Sie im Bereich zu aktualisieren.|  
|[CFrameWndEx::OnWindowPosChanged](#onwindowposchanged)|Wird vom Framework aufgerufen, wenn die Größe, Position oder Z-Reihenfolge wegen eines Aufrufs einer Verwaltungsmethode Fenster geändert hat.|  
|[CFrameWndEx::PaneFromPoint](#panefrompoint)|Gibt die andockbaren Bereich, der den angegebenen Punkt enthält.|  
|[CFrameWndEx::PreTranslateMessage](#pretranslatemessage)|Bestimmte Windows-Meldungen verarbeitet, bevor sie verteilt wurden.|  
|[CFrameWndEx::RecalcLayout](#recalclayout)|Passt das Layout des Rahmens und zugehöriges untergeordnetes Fenster.|  
|[CFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|Hebt die Registrierung eines Bereichs, und entfernt sie aus der internen Liste in der Dockingstation-Manager.|  
|[CFrameWndEx::SetDockState](#setdockstate)|Stellt wieder her, das Andocken Layout Andocken in der Registrierung gespeichert.|  
|[CFrameWndEx::SetPrintPreviewFrame](#setprintpreviewframe)|Legt das Rahmenfenster Seitenansicht.|  
|[CFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|Fügt eine benutzerdefinierte Befehle in einem Symbolleistenmenü.|  
|[CFrameWndEx::ShowFullScreen](#showfullscreen)|Schaltet den Hauptframe zwischen Vollbild und die regulären.|  
|[CFrameWndEx::ShowPane](#showpane)|Anzeigen oder ausblenden im angegebenen Bereich.|  
|[CFrameWndEx::UpdateCaption](#updatecaption)|Aufgerufen, um die Beschriftung des Fensters Frame zu aktualisieren.|  
|[CFrameWndEx::WinHelp](#winhelp)|Ruft entweder die `WinHelp` Anwendung oder der Kontext verbundene Hilfe.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine Klasse von erben die `CFrameWndEx` Klasse. Das Beispiel veranschaulicht die Methodensignaturen in der Unterklasse und das Überschreiben der `OnShowPopupMenu` Methode. Dieser Codeausschnitt ist Teil der [WordPad-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&3;](../../mfc/reference/codesnippet/cpp/cframewndex-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad&4;](../../mfc/reference/codesnippet/cpp/cframewndex-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CFrameWndEx](../../mfc/reference/cframewndex-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxframewndex.h  
  
##  <a name="a-nameactiveitemrecalclayouta--cframewndexactiveitemrecalclayout"></a><a name="activeitemrecalclayout"></a>CFrameWndEx::ActiveItemRecalcLayout  
 Passt das Layout der OLE-Clientelement und den Rand des Clientbereichs.  
  
```  
void ActiveItemRecalcLayout();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameaddpanea--cframewndexaddpane"></a><a name="addpane"></a>CFrameWndEx::AddPane  
 Registriert eine Steuerleiste docking-Manager.  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 Ein Steuerelement-Leistenbereich zu registrieren.  
  
 [in] `bTail`  
 `TRUE`Wenn Sie das Steuerelement Leistenbereich bis zum Ende der Liste hinzufügen möchten; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Steuerleiste erfolgreich registriert wurde. `FALSE` andernfalls.  
  
##  <a name="a-nameadjustdockinglayouta--cframewndexadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CFrameWndEx::AdjustDockingLayout  
 Berechnet das Layout für alle Bereiche, die an das Rahmenfenster angedockt sind.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hdwp`  
 Ein Handle für eine Struktur, die die Positionen von Fenstern enthält. .  
  
### <a name="remarks"></a>Hinweise  
 Die Struktur Hdwp wird initialisiert, indem die [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) Methode.  
  
##  <a name="a-namedelayupdateframemenua--cframewndexdelayupdateframemenu"></a><a name="delayupdateframemenu"></a>CFrameWndEx::DelayUpdateFrameMenu  
 Legt die Frame-Menü und dann aktualisiert, wenn befehlsverarbeitung im Leerlauf befindet.  
  
```  
virtual void DelayUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMenuAlt`  
 Handle für einen alternativen Menüs.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedockpanea--cframewndexdockpane"></a><a name="dockpane"></a>CFrameWndEx::DockPane  
 Das Rahmenfenster im angegebenen Bereich angedockt.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID=0,  
    LPCRECT lpRect=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf die Steuerleiste angedockt werden.  
  
 [in] `nDockBarID`  
 Die ID der Seite der Rahmenfenster angedockt werden soll.  
  
 [in] `lpRect`  
 Ein Zeiger auf eine Konstante Rect-Struktur, die Bildschirmposition und Größe des Fensters angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die `nDockBarID` Parameter kann einen der folgenden Werte aufweisen:  
  
-   AFX_IDW_DOCKBAR_TOP  
  
-   AFX_IDW_DOCKBAR_BOTTOM  
  
-   AFX_IDW_DOCKBAR_LEFT  
  
-   AFX_IDW_DOCKBAR_RIGHT  
  
##  <a name="a-namedockpaneleftofa--cframewndexdockpaneleftof"></a><a name="dockpaneleftof"></a>CFrameWndEx::DockPaneLeftOf  
 Dockt den angegebenen Bereich links von einem anderen Bereich an.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf das Objekt im Bereich angedockt werden.  
  
 [in] `pLeftOf`  
 Ein Zeiger auf den Bereich auf der linken Seite, die den angegebenen Bereich anzudocken `pBar`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn `pBar` erfolgreich angedockt ist. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode nimmt die Symbolleiste anhand der `pBar` Parameter und es auf der linken Seite der Symbolleiste anhand des Docks `pLeftOf` Parameter.  
  
##  <a name="a-nameenableautohidepanesa--cframewndexenableautohidepanes"></a><a name="enableautohidepanes"></a>CFrameWndEx::EnableAutoHidePanes  
 Ermöglicht das automatische ausblenden im Modus für den Bereich an der angegebenen Seite des Hauptrahmenfenster angedockten.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwDockStyle`  
 Gibt die Seite das Hauptrahmenfenster, um den Bereich anzudocken.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine Leiste Bereich angedockt ist erfolgreich der Frame-Fenster-Seite, die durch angegebenen `dwDockStyle`, `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 `dwDockStyle`Dabei kann es sich um einen der folgenden Werte aufweisen:  
  
-   CBRS_ALIGN_TOP: ermöglicht die Steuerleiste am Anfang der Clientbereich eines Rahmenfensters angedockt werden.  
  
-   CBRS_ALIGN_BOTTOM: ermöglicht die Steuerleiste am unteren Rand der Clientbereich eines Rahmenfensters angedockt werden.  
  
-   CBRS_ALIGN_LEFT: ermöglicht die Steuerleiste an der linken Seite des Clientbereichs eines Rahmenfensters angedockt werden.  
  
-   CBRS_ALIGN_RIGHT: ermöglicht die Steuerleiste an der rechten Seite des Clientbereichs eines Rahmenfensters angedockt werden.  
  
##  <a name="a-nameenabledockinga--cframewndexenabledocking"></a><a name="enabledocking"></a>CFrameWndEx::EnableDocking  
 Ermöglicht das Andocken der Bereiche des Rahmenfensters.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwDockStyle`  
 Gibt die Seite das Hauptrahmenfenster, in dem die Bereich Leiste angedockt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine Leiste Bereich erfolgreich auf der angegebenen Seite angedockt werden kann. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `dwDockStyle` Parameter kann einen der folgenden Werte aufweisen:  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="a-nameenablefullscreenmainmenua--cframewndexenablefullscreenmainmenu"></a><a name="enablefullscreenmainmenu"></a>CFrameWndEx::EnableFullScreenMainMenu  
 Anzeigen oder ausblenden im Hauptmenü in einem Vollbild-Modus.  
  
```  
void EnableFullScreenMainMenu(BOOL bEnableMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnableMenu`  
 `TRUE`im Vollbildmodus, im Hauptmenü anzeigen `FALSE` andernfalls.  
  
##  <a name="a-nameenablefullscreenmodea--cframewndexenablefullscreenmode"></a><a name="enablefullscreenmode"></a>CFrameWndEx::EnableFullScreenMode  
 Ermöglicht den Vollbildmodus für das Rahmenfenster.  
  
```  
void EnableFullScreenMode(UINT uiFullScreenCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiFullScreenCmd`  
 Die ID eines Befehls, der aktiviert und deaktiviert den Vollbildmodus.  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie in den Vollbildmodus alle andockbarer Steuerleisten, Symbolleisten und Menüs ausgeblendet, und die aktive Ansicht wird angepasst, um den Vollbildmodus zu belegen.  
  
 Wenn Sie den Vollbildmodus aktivieren, müssen Sie eine Befehls-ID angeben, die aktiviert oder deaktiviert den Vollbildmodus. Rufen Sie `EnableFullScreenMode` aus des Hauptframe `OnCreate` Funktion. Wenn ein Rahmenfenster zum Vollbild-Modus wechselt, erstellt das Framework eine mit einer Schaltfläche mit der angegebenen Befehls-ID.  
  
 Wenn Sie im Hauptmenü auf dem Bildschirm angezeigt werden sollen, rufen Sie [CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu).  
  
##  <a name="a-nameenableloaddockstatea--cframewndexenableloaddockstate"></a><a name="enableloaddockstate"></a>CFrameWndEx::EnableLoadDockState  
 Aktiviert oder deaktiviert das Laden der Andockstatus.  
  
```  
void EnableLoadDockState(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie das Laden der Andockstatus `FALSE` das Laden der Andockstatus deaktivieren.  
  
##  <a name="a-nameenablepanemenua--cframewndexenablepanemenu"></a><a name="enablepanemenu"></a>CFrameWndEx::EnablePaneMenu  
 Aktiviert oder deaktiviert die automatische Behandlung von klicken Sie im Bereich.  
  
```  
void EnablePaneMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeLabel,  
    UINT uiViewToolbarsMenuEntryID,  
    BOOL bContextMenuShowsToolbarsOnly=FALSE,  
    BOOL bViewMenuShowsToolbarsOnly=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die automatische Behandlung von der Steuerleiste Popupmenüs; `FALSE` So deaktivieren Sie die automatische Behandlung von der Steuerleiste Popup-Menüs.  
  
 [in] `uiCustomizeCmd`  
 Die Befehls-ID, der die **anpassen** Menüelement.  
  
 [in] `strCustomizeLabel`  
 Die Bezeichnung für angezeigt werden die **anpassen** Menüelement  
  
 [in] `uiViewToolbarsMenuEntryID`  
 Die ID eines Menüelements Symbolleiste, die Sie im Popupmenü in der Steuerleiste geöffnet wird.  
  
 [in] `bContextMenuShowsToolbarsOnly`  
 Wenn `TRUE`, die Steuerleiste Kontextmenü zeigt die Liste der Symbolleisten nur. Wenn `FALSE`, klicken Sie im Menü zeigt die Liste der Symbolleisten und die Dockingstation Balken.  
  
 [in] `bViewMenuShowsToolbarsOnly`  
 Wenn `TRUE`, Systemmenü Balken zeigt die Liste der Symbolleisten nur. Wenn `FALSE`, klicken Sie im Menü zeigt die Liste der Symbolleisten und die Dockingstation Balken.  
  
##  <a name="a-namegetactivepopupa--cframewndexgetactivepopup"></a><a name="getactivepopup"></a>CFrameWndEx::GetActivePopup  
 Gibt einen Zeiger auf den momentan angezeigten Popupmenü.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die aktuell angezeigten Popupmenü; andernfalls `NULL`.  
  
##  <a name="a-namegetdefaultresida--cframewndexgetdefaultresid"></a><a name="getdefaultresid"></a>CFrameWndEx::GetDefaultResId  
 Gibt die Ressourcen-ID, die Sie angegeben, wenn das Framework das Rahmenfenster geladen.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ressourcen-ID-Wert, der vom Benutzer angegeben werden, wenn das Framework das Rahmenfenster geladen. 0 (null), wenn das Rahmenfenster keinen Menüleiste.  
  
##  <a name="a-namegetdockingmanagera--cframewndexgetdockingmanager"></a><a name="getdockingmanager"></a>CFrameWndEx::GetDockingManager  
 Ruft die [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) Objekt für das Rahmenfenster.  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Das Rahmenfenster erstellt und verwendet einen [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) um untergeordnete Fenster andocken zu verwalten.  
  
##  <a name="a-namegetmenubara--cframewndexgetmenubar"></a><a name="getmenubar"></a>CFrameWndEx::GetMenuBar  
 Gibt einen Zeiger auf das Menüleistenobjekt zurück, das an das Rahmenfenster angefügt ist.  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Menü Bar-Objekt an das Rahmenfenster angefügt.  
  
##  <a name="a-namegetpanea--cframewndexgetpane"></a><a name="getpane"></a>CFrameWndEx::GetPane  
 Gibt einen Zeiger auf den Bereich, der die angegebene ID verfügt.  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Die Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Bereich, der die angegebene ID verfügt. `NULL`Wenn kein solcher Bereich vorhanden ist.  
  
##  <a name="a-namegetribbonbara--cframewndexgetribbonbar"></a><a name="getribbonbar"></a>CFrameWndEx::GetRibbonBar  
 Ruft die Menüband-Steuerelement für den Rahmen.  
  
```  
CMFCRibbonBar* GetRibbonBar();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) für den Frame.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegettearoffbarsa--cframewndexgettearoffbars"></a><a name="gettearoffbars"></a>CFrameWndEx::GetTearOffBars  
 Gibt eine Liste von Bereichsobjekten zurück, die sich in einem abtrennbaren Zustand befinden.  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf `CObList` -Objekt, das eine Auflistung von Zeigern auf die Bereich-Objekte enthält, die in einem Zustand abtrennbare sind.  
  
##  <a name="a-namegettoolbarbuttontooltiptexta--cframewndexgettoolbarbuttontooltiptext"></a><a name="gettoolbarbuttontooltiptext"></a>CFrameWndEx::GetToolbarButtonToolTipText  
 Vom Framework aufgerufen, wenn die Anwendung die QuickInfo für eine Symbolleisten-Schaltfläche angezeigt wird.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf eine Symbolleisten-Schaltfläche.  
  
 [in] `strTTText`  
 Der QuickInfo-Text für die Schaltfläche angezeigt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die QuickInfo angezeigt wird. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig bewirkt diese Methode nichts. Überschreiben Sie diese Methode, wenn die QuickInfo für die Symbolleisten-Schaltfläche angezeigt werden soll.  
  
##  <a name="a-nameinsertpanea--cframewndexinsertpane"></a><a name="insertpane"></a>CFrameWndEx::InsertPane  
 Setzt einen Bereich in eine Liste von Steuerleisten ein und registriert ihn beim Dock-Manager.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pControlBar`  
 Ein Zeiger auf eine Steuerleiste, die in die Liste der Steuerleisten eingefügt und beim Dock-Manager registriert werden soll.  
  
 `pTarget`  
 Ein Zeiger auf eine Steuerleiste vor oder hinter der der Bereich eingefügt werden soll.  
  
 `bAfter`  
 `TRUE`Wenn Sie einfügen möchten `pControlBar` nach `pTarget`, `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Steuerleiste wurde erfolgreich eingefügt und registriert, `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen jede Steuerleiste registrieren, indem die [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) ein zur Teilnahme an der andocklayout.  
  
##  <a name="a-nameisfullscreena--cframewndexisfullscreen"></a><a name="isfullscreen"></a>CFrameWndEx::IsFullScreen  
 Bestimmt, ob das Rahmenfenster im Vollbildmodus ausgeführt wird.  
  
```  
BOOL IsFullScreen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Rahmenfenster im Vollbildmodus ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können den Vollbildmodus festlegen, durch Aufrufen der [CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode) Methode.  
  
##  <a name="a-nameismenubaravailablea--cframewndexismenubaravailable"></a><a name="ismenubaravailable"></a>CFrameWndEx::IsMenuBarAvailable  
 Bestimmt, ob der Zeiger auf das Menü Bar-Objekt gültig ist.  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Rahmenfenster Menüleiste enthält. andernfalls `FALSE`.  
  
##  <a name="a-nameispointneardocksitea--cframewndexispointneardocksite"></a><a name="ispointneardocksite"></a>CFrameWndEx::IsPointNearDockSite  
 Bestimmt, ob der Punkt in einer Zone Ausrichtung befindet.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die Position des Punkts.  
  
 [out] `dwBarAlignment`  
 Wobei der Punkt ausgerichtet ist. Siehe die Tabelle im Abschnitt mit Hinweisen für mögliche Werte.  
  
 [out] `bOuterEdge`  
 `TRUE`Wenn der Punkt befindet schließen Sie auf den Rahmen. `FALSE` Wenn der Punkt in einen Clientbereich befindet.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Punkt in einer Zone Ausrichtung befindet; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Werte für die `dwBarAlignment` Parameter.  
  
 `CBRS_ALIGN_TOP`  
 Oben ausgerichtet.  
  
 `CBRS_ALIGN_RIGHT`  
 Rechts ausgerichtet.  
  
 `CBRS_ALIGN_BOTTOM`  
 Unten ausgerichtet.  
  
 `CBRS_ALIGN_LEFT`  
 Links ausgerichtet.  
  
##  <a name="a-nameisprintpreviewa--cframewndexisprintpreview"></a><a name="isprintpreview"></a>CFrameWndEx::IsPrintPreview  
 Bestimmt, ob das Rahmenfenster im Seitenansichtsmodus.  
  
```  
BOOL IsPrintPreview();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Rahmenfenster im Seitenansichtsmodus ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameloadframea--cframewndexloadframe"></a><a name="loadframe"></a>CFrameWndEx::LoadFrame  
 Diese Methode wird aufgerufen, nachdem Konstruktion Rahmenfenster erstellen und Laden ihre Ressourcen.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIDResource`  
 Die Ressourcen-ID, die zum Laden von Ressourcen für alle Rahmen verwendet wird.  
  
 [in] `dwDefaultStyle`  
 Der Standard-Frame-Fensterstil.  
  
 [in] `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster des Frames.  
  
 [in] `pContext`  
 Zeiger auf eine [angegeben ist und Struktur](../../mfc/reference/ccreatecontext-structure.md) -Klasse, die vom Framework während der anwendungserstellung verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn die Methode erfolgreich ausgeführt wurde, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namenegotiateborderspacea--cframewndexnegotiateborderspace"></a><a name="negotiateborderspace"></a>CFrameWndEx::NegotiateBorderSpace  
 Implementiert OLE-Client Rahmen aushandeln.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nBorderCmd`  
 Der Befehl für den Rahmen-Aushandlung. Finden Sie im Abschnitt "Hinweise" für die möglichen Werte.  
  
 [in, out] `lpRectBorder`  
 Die Dimensionen des Rahmens.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Layout neu berechnet werden muss; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Werte für die `nBorderCmd` Parameter.  
  
 `borderGet`  
 Abgerufen Sie Speicherplatz für OLE-Client werden.  
  
 `borderRequest`  
 Erfordern Sie OLE-Client-Speicherplatz.  
  
 `borderSet`  
 Legen Sie die OLE-Client-Speicherplatz.  
  
##  <a name="a-nameonactivatea--cframewndexonactivate"></a><a name="onactivate"></a>CFrameWndEx::OnActivate  
 Das Framework ruft diese Methode auf, wenn Benutzereingaben zu oder von der Frame gewechselt wird.  
  
```  
afx_msg void OnActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nState`  
 Gibt an, ob der Frame aktiv oder inaktiv ist. Siehe die Tabelle im Abschnitt mit Hinweisen für mögliche Werte.  
  
 [in] `pWndOther`  
 Zeiger auf ein anderes Fenster, das Benutzereingaben mit der aktuellen Instanz angeschlossen ist.  
  
 [in] `bMinimized`  
 Minimierten Zustand des Frames. `TRUE`Wenn der Frame minimiert wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Werte für die `nState` Parameter.  
  
 `WA_ACTIVE`  
 Der Rahmen wird von einer anderen Methode als ein Mausklick ausgewählt.  
  
 `WA_CLICKACTIVE`  
 Der Rahmen wird durch einen Mausklick ausgewählt.  
  
 `WA_INACTIVE`  
 Der Rahmen ist nicht aktiviert.  
  
##  <a name="a-nameonactivateappa--cframewndexonactivateapp"></a><a name="onactivateapp"></a>CFrameWndEx::OnActivateApp  
 Wird vom Framework aufgerufen, wenn die Anwendung aktiviert oder deaktiviert ist.  
  
```  
afx_msg void OnActivateApp(
    BOOL bActive,  
    DWORD dwThreadID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActive`  
 `TRUE`Wenn die Anwendung ausgewählt ist. `FALSE` , wenn die Anwendung nicht aktiviert ist.  
  
 [in] `dwThreadID`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonchangevisualmanagera--cframewndexonchangevisualmanager"></a><a name="onchangevisualmanager"></a>CFrameWndEx::OnChangeVisualManager  
 Wird vom Framework aufgerufen, wenn eine Änderung des Frames, eine Änderung an der visuellen Manager erfordert.  
  
```  
afx_msg LRESULT OnChangeVisualManager(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wParam`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `lParam`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonclosea--cframewndexonclose"></a><a name="onclose"></a>CFrameWndEx::OnClose  
 Das Framework ruft diese Methode, um den Rahmen zu schließen.  
  
```  
afx_msg void OnClose();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Frame im Seitenansichtsmodus ist, sendet er eine Windows-Meldung zum Schließen der Seitenansicht; Wenn der Frame ein OLE-Clients hostet, wird, der Client deaktiviert.  
  
##  <a name="a-nameonclosedockingpanea--cframewndexonclosedockingpane"></a><a name="onclosedockingpane"></a>CFrameWndEx::OnCloseDockingPane  
 Vom Framework aufgerufen, wenn der Benutzer klickt auf die **schließen** auf einen andockbaren Bereich auf die Schaltfläche.  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane* pPane);
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die andockleiste geschlossen werden kann. `FALSE`andernfalls  
  
### <a name="remarks"></a>Hinweise  
 Implementiert die Standardeinstellung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode, wenn Sie das Ausblenden der andockleiste behandeln möchten.  
  
##  <a name="a-nameoncloseminiframea--cframewndexoncloseminiframe"></a><a name="oncloseminiframe"></a>CFrameWndEx::OnCloseMiniFrame  
 Vom Framework aufgerufen, wenn der Benutzer klickt auf die **schließen** Schaltfläche auf einem schwebenden Mini-Rahmenfenster.  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein Gleitkomma Mini Rahmenfenster geschlossen werden kann. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode, wenn Sie das Ausblenden eines frei verschiebbaren Mini Rahmenfensters verarbeiten möchten.  
  
##  <a name="a-nameonclosepopupmenua--cframewndexonclosepopupmenu"></a><a name="onclosepopupmenu"></a>CFrameWndEx::OnClosePopupMenu  
 Wird vom Framework aufgerufen, wenn ein aktives Popupmenü eine WM_DESTROY-Meldung verarbeitet.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Parameter  
 `pMenuPopup`  
 Ein Zeiger auf ein Popup-Menü.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework sendet eine Nachricht WM_DESTROY, wenn es gerade das Fenster zu schließen. Überschreiben Sie diese Methode, wenn Sie Nachrichten aus dem behandeln möchten `CMFCPopupMenu` Objekte, die an das Rahmenfenster gehören bei einer `CMFCPopupMenu` -Objekt verarbeitet eine `WM_DESTROY` vom Framework gesendet wird, wenn das Fenster geschlossen wird.  
  
##  <a name="a-nameoncmdmsga--cframewndexoncmdmsg"></a><a name="oncmdmsg"></a>CFrameWndEx::OnCmdMsg  
 Sendet Nachrichten-Befehl.  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Die Befehls-ID.  
  
 [in] `nCode`  
 Kategorie angezeigt.  
  
 [in, out] `pExtra`  
 Ein Zeiger auf ein Command-Objekt.  
  
 [in, out] `pHandlerInfo`  
 Ein Zeiger auf einen Handler Befehlsstruktur.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Befehlsnachricht verarbeitet wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameoncontexthelpa--cframewndexoncontexthelp"></a><a name="oncontexthelp"></a>CFrameWndEx::OnContextHelp  
 Vom Framework aufgerufen Kontext bezogenen Hilfe anzuzeigen.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameoncreatea--cframewndexoncreate"></a><a name="oncreate"></a>CFrameWndEx::OnCreate  
 Wird vom Framework aufgerufen, nachdem der Rahmen erstellt wurde.  
  
```  
afx_msg int OnCreate(LPCREATESTRUCT lpCreateStruct);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpCreateStruct`  
 Ein Zeiger auf die [CREATESTRUCT-Struktur](../../mfc/reference/createstruct-structure.md) für den neuen Rahmen.  
  
### <a name="return-value"></a>Rückgabewert  
 0 die Frame-Erstellung fortsetzen;&1;, um den Frame zu zerstören.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondestroya--cframewndexondestroy"></a><a name="ondestroy"></a>CFrameWndEx::OnDestroy  
 Wird vom Framework aufgerufen, wenn der Frame zerstört wird.  
  
```  
afx_msg void OnDestroy();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Zugriffstastentabelle und alle Fenster werden zerstört.  
  
##  <a name="a-nameondrawmenuimagea--cframewndexondrawmenuimage"></a><a name="ondrawmenuimage"></a>CFrameWndEx::OnDrawMenuImage  
 Wird vom Framework aufgerufen, wenn die Anwendung das ein Menüelement zugeordnete Bild zeichnet.  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuButton,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pMenuButton`  
 Ein Zeiger auf eine Schaltfläche, deren Bild gerendert wird.  
  
 [in] `rectImage`  
 Ein Zeiger auf eine `Rect` -Struktur, die Bildschirmposition und Größe des Bilds angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Framework erfolgreich das Bild rendert. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn das Image-Rendering für die Menüelemente anpassen, die auf der Menüleiste, die im Besitz von gehören sollen die `CFrameWndEx` abgeleitetes Objekt.  
  
##  <a name="a-nameondrawmenulogoa--cframewndexondrawmenulogo"></a><a name="ondrawmenulogo"></a>CFrameWndEx::OnDrawMenuLogo  
 Aufgerufen, wenn ein `CMFCPopupMenu` Objekt eine WM_PAINT-Meldung verarbeitet.  
  
```  
virtual void OnDrawMenuLogo(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    const CRect& rectLogo);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pMenu`  
 Ein Zeiger auf das Menüelement.  
  
 [in] `rectLogo`  
 Ein Verweis auf eine Konstante `CRect` -Struktur, die Bildschirmposition und Größe des Logos Menü angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie möchten ein Logo im Popupmenü anzeigen, die auf der Menüleiste, die im Besitz von gehört die `CFrameWndEx` abgeleitetes Objekt.  
  
##  <a name="a-nameondwmcompositionchangeda--cframewndexondwmcompositionchanged"></a><a name="ondwmcompositionchanged"></a>CFrameWndEx::OnDWMCompositionChanged  
 Wird vom Framework aufgerufen, wenn Desktop Window Manager (DWM) Komposition aktiviert oder deaktiviert wurde.  
  
```  
afx_msg LRESULT OnDWMCompositionChanged(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wp`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `lp`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonexitsizemovea--cframewndexonexitsizemove"></a><a name="onexitsizemove"></a>CFrameWndEx::OnExitSizeMove  
 Vom Framework aufgerufen, wenn der Frame beendet wird, verschieben oder dessen Größe ändern.  
  
```  
LRESULT OnExitSizeMove(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wp`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `lp`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameongetminmaxinfoa--cframewndexongetminmaxinfo"></a><a name="ongetminmaxinfo"></a>CFrameWndEx::OnGetMinMaxInfo  
 Wird vom Framework aufgerufen, wenn Frames Größe an Fenster Dimension begrenzen.  
  
```  
afx_msg void OnGetMinMaxInfo(MINMAXINFO FAR* lpMMI);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpMMI`  
 Zeiger auf eine [MINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632605) Struktur.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonidleupdatecmduia--cframewndexonidleupdatecmdui"></a><a name="onidleupdatecmdui"></a>CFrameWndEx::OnIdleUpdateCmdUI  
 Vom Framework aufgerufen, die die Frame-Anzeige zu aktualisieren, wenn befehlsverarbeitung im Leerlauf befindet.  
  
```  
afx_msg LRESULT OnIdleUpdateCmdUI(
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wParam`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `lParam`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonlbuttondowna--cframewndexonlbuttondown"></a><a name="onlbuttondown"></a>CFrameWndEx::OnLButtonDown  
 Das Framework ruft diese Methode auf, wenn der Benutzer die linke Maustaste drückt.  
  
```  
afx_msg void OnLButtonDown(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFlags`  
 Gibt an, ob der Benutzer Modifizierertasten gedrückt. Mögliche Werte finden Sie in den Parameter `wParam` in [WM_LBUTTONDOWN Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms645607).  
  
 [in] `point`  
 Gibt die x und y-Koordinaten des Mauszeigers, relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonlbuttonupa--cframewndexonlbuttonup"></a><a name="onlbuttonup"></a>CFrameWndEx::OnLButtonUp  
 Das Framework ruft diese Methode auf, wenn der Benutzer die linke Maustaste loslässt.  
  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFlags`  
 Gibt an, ob der Benutzer Modifizierertasten gedrückt. Mögliche Werte finden Sie in den Parameter `wParam` in [WM_LBUTTONUP Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms645608).  
  
 [in] `point`  
 Gibt die x und y-Koordinaten des Mauszeigers, relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonmenubuttontoolhittesta--cframewndexonmenubuttontoolhittest"></a><a name="onmenubuttontoolhittest"></a>CFrameWndEx::OnMenuButtonToolHitTest  
 Vom Framework aufgerufen wird bei einer `CMFCToolBarButton` -Objekt Prozesse eine `WM_NCHITTEST` Nachricht.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf die Symbolleisten-Schaltfläche.  
  
 [out] `pTI`  
 Ein Zeiger auf eine Struktur Tool.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Anwendung füllt die `pTI` Parameter. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie eine QuickInfo-Informationen zu einem bestimmten Menüelement bereitstellen möchten.  
  
##  <a name="a-nameonmenuchara--cframewndexonmenuchar"></a><a name="onmenuchar"></a>CFrameWndEx::OnMenuChar  
 Vom Framework aufgerufen, wenn ein Menü angezeigt wird und der Benutzer drückt einen Schlüssel, der nicht an einen Befehl.  
  
```  
afx_msg LRESULT OnMenuChar(
    UINT nChar,  
    UINT nFlags,  
    CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nChar`  
 Zeichencode der gedrückten Taste.  
  
 [in] `nFlags`  
 Enthält die `MF_POPUP` Flag ist das angezeigte Menü ein Untermenü; enthält die `MF_SYSMENU` flag des Menüs ein Systemmenü ist.  
  
 [in] `pMenu`  
 Ein Zeiger auf ein Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 Das höherwertige Wort muss einer der folgenden Werte sein.  
  
 `0`  
 Das Framework sollte die Tastatureingabe ignoriert werden.  
  
 `1`  
 Das Framework sollte das Menü zu schließen.  
  
 `2`  
 Das Framework sollte eines der Elemente, die angezeigt wird, klicken Sie im Menü wählen. Das niederwertige Wort enthält die ID des Befehls auswählen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonmousemovea--cframewndexonmousemove"></a><a name="onmousemove"></a>CFrameWndEx::OnMouseMove  
 Das Framework ruft diese Methode auf, wenn der Mauszeiger bewegt wird.  
  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFlags`  
 Gibt an, ob ein Benutzer Modifizierertasten gedrückt. Mögliche Werte finden Sie in den Parameter `wParam` in [WM_MOUSEMOVE Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms645616).  
  
 [in] `point`  
 Gibt die x- und y Koordinaten des Mauszeigers in Bezug auf die linke obere Ecke des Fensters.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonmoveminiframea--cframewndexonmoveminiframe"></a><a name="onmoveminiframe"></a>CFrameWndEx::OnMoveMiniFrame  
 Vom Framework aufgerufen, wenn ein Fenster verschoben wird.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFrame`  
 Zeiger auf die [CPaneFrameWnd Klasse](../../mfc/reference/cpaneframewnd-class.md) Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Fenster nicht angedockt wurde; `FALSE` , wenn das Fenster angedockt ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonncactivatea--cframewndexonncactivate"></a><a name="onncactivate"></a>CFrameWndEx::OnNcActivate  
 Wird vom Framework aufgerufen, wenn der nicht-Clientbereich des Rahmens neu gezeichnet werden muss, um eine Änderung im aktiven Zustand anzuzeigen.  
  
```  
afx_msg BOOL OnNcActivate(BOOL bActive);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActive`  
 `TRUE`um den aktiven Frame zu zeichnen. `FALSE` den inaktiven Rahmen gezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Fortsetzen der Verarbeitung standardmäßig einen Wert ungleich null; 0, um zu verhindern, dass der nicht-Clientbereich wird deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonnccalcsizea--cframewndexonnccalcsize"></a><a name="onnccalcsize"></a>CFrameWndEx::OnNcCalcSize  
 Wird vom Framework aufgerufen, wenn die Größe und Position des Clientbereichs berechnet werden müssen.  
  
```  
afx_msg void OnNcCalcSize(
    BOOL bCalcValidRects,  
    NCCALCSIZE_PARAMS FAR* lpncsp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCalcValidRects`  
 `TRUE`Wenn die Anwendung einen gültigen Clientbereich angeben müssen; andernfalls `FALSE`.  
  
 [in] `lpncsp`  
 Zeiger auf eine `NCCALCSIZE_PARAMS` -Struktur, die Dimension geändert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonnchittesta--cframewndexonnchittest"></a><a name="onnchittest"></a>CFrameWndEx::OnNcHitTest  
 Wird vom Framework aufgerufen, wenn der Mauszeiger bewegt wird, oder wenn eine Maustaste gedrückt oder losgelassen wird.  
  
```  
afx_msg LRESULT OnNcHitTest(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die Position des Mauszeigers in Bildschirmkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger erreicht Enumerationswert. Eine Liste der möglichen Werte finden Sie unter [WM_NCHITTEST Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms645618).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonncmousemovea--cframewndexonncmousemove"></a><a name="onncmousemove"></a>CFrameWndEx::OnNcMouseMove  
 Wird vom Framework aufgerufen, wenn der Mauszeiger in einem nicht-Clientbereich.  
  
```  
afx_msg void OnNcMouseMove(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHitTest`  
 Ein Zeiger erreicht Enumerationswert. Eine Liste der möglichen Werte finden Sie unter [WM_NCHITTEST Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms645618).  
  
 [in] `point`  
 Die Position des Mauszeigers in Bildschirmkoordinaten.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonncpainta--cframewndexonncpaint"></a><a name="onncpaint"></a>CFrameWndEx::OnNcPaint  
 Wird vom Framework aufgerufen, wenn der nicht-Clientbereich gezeichnet werden muss.  
  
```  
afx_msg void OnNcPaint();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonpanechecka--cframewndexonpanecheck"></a><a name="onpanecheck"></a>CFrameWndEx::OnPaneCheck  
 Aufgerufen, um die Sichtbarkeit eines Bereichs zu steuern.  
  
```  
afx_msg BOOL OnPaneCheck(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Steuerelement-ID eines Bereichs.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Befehl behandelt wurde. `FALSE` befehlsverarbeitung fortsetzen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonpostpreviewframea--cframewndexonpostpreviewframe"></a><a name="onpostpreviewframe"></a>CFrameWndEx::OnPostPreviewFrame  
 Wird vom Framework aufgerufen, wenn der Benutzer den Seitenansichtmodus ändert.  
  
```  
afx_msg LRESULT OnPostPreviewFrame(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wParam`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `lParam`  
 `TRUE`Wenn der Frame im Seitenansichtsmodus ist. `FALSE` Wenn Seitenansichtsmodus deaktiviert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonpowerbroadcasta--cframewndexonpowerbroadcast"></a><a name="onpowerbroadcast"></a>CFrameWndEx::OnPowerBroadcast  
 Vom Framework aufgerufen, wenn ein Power Management-Ereignis eintritt.  
  
```  
afx_msg LRESULT OnPowerBroadcast(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wp`  
 Das Power Management-Ereignis. Eine Liste der möglichen Werte finden Sie unter [WM_POWERBROADCAST-Meldung](http://msdn.microsoft.com/library/windows/desktop/aa373247).  
  
 [in] `lp`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Führen Sie die Standardfensterprozedur aufrufen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonsetmenua--cframewndexonsetmenu"></a><a name="onsetmenu"></a>CFrameWndEx::OnSetMenu  
 Vom Framework aufgerufen wird im Menü Fenster Frame zu ersetzen.  
  
```  
afx_msg LRESULT OnSetMenu(
    WPARAM wp,  
    LPARAM lp);  
  
BOOL OnSetMenu(HMENU hmenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wp`  
 Handle für das neue Bild Fenstermenü.  
  
 [in] `lp`  
 Handle für das neue Menü "Fenster".  
  
 [in] `hmenu`  
 Handle für das neue Bild Fenstermenü.  
  
### <a name="return-value"></a>Rückgabewert  
 `LRESULT`ist das Ergebnis des Aufrufs von der Standardfensterprozedur.  
  
 `BOOL`ist `TRUE` war das Ereignis behandelt, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonsetpreviewmodea--cframewndexonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CFrameWndEx::OnSetPreviewMode  
 Vom Framework aufgerufen wird zum Festlegen des Modus "Seitenansicht" für den Frame.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bPreview`  
 `TRUE`So aktivieren Sie die Seitenansicht; `FALSE` Seitenansicht deaktivieren.  
  
 [in] `pState`  
 Zeiger auf eine `CPrintPreviewState` Statusstruktur frame.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonsettexta--cframewndexonsettext"></a><a name="onsettext"></a>CFrameWndEx::OnSetText  
 Aufgerufen, um den Text eines Fensters festzulegen.  
  
```  
afx_msg LRESULT OnSetText(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wParam`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `lParam`  
 Zeiger auf den Text für das Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabewert bei einem Aufruf von [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonshowcustomizepanea--cframewndexonshowcustomizepane"></a><a name="onshowcustomizepane"></a>CFrameWndEx::OnShowCustomizePane  
 Vom Framework aufgerufen, wenn es zeigt eine `QuickCustomizePane`.  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenuPane`  
 Ein Zeiger auf die schnelle anpassen, Bereich.  
  
 [in] `uiToolbarID`  
 Die Steuerelement-ID der Symbolleiste anpassen.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Schnelles anpassen Menü ist ein Popup-Menü, das angezeigt wird, wenn Sie auf der Symbolleiste auf die Schaltfläche Anpassen  
  
##  <a name="a-nameonshowpanesa--cframewndexonshowpanes"></a><a name="onshowpanes"></a>CFrameWndEx::OnShowPanes  
 Vom Framework aufgerufen wird, anzeigen oder Ausblenden von Bereichen.  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 `TRUE`Wenn die Anwendung die Bereiche dargestellt; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode immer `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung zeigt die Bereiche Wenn `bShow` ist `TRUE` und die Bereiche ausgeblendet sind oder wenn `bShow` ist `FALSE` und die Bereiche sichtbar sind.  
  
 Die standardmäßige Implementierung Blendet die Bereiche aus, wenn `bShow` ist `TRUE` und die Bereiche sichtbar sind oder wenn `bShow` ist `FALSE` und die Bereiche ausgeblendet werden.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, benutzerdefinierten Code auszuführen, wenn das Framework Blendet Bereiche.  
  
##  <a name="a-nameonshowpopupmenua--cframewndexonshowpopupmenu"></a><a name="onshowpopupmenu"></a>CFrameWndEx::OnShowPopupMenu  
 Wird vom Framework aufgerufen, wenn ein Popup-Menü angezeigt.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenu`  
 Ein Zeiger auf ein Popup-Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie im Popupmenü sichtbar ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, benutzerdefinierten Code auszuführen, wenn das Framework ein Popupmenü angezeigt. Beispielsweise überschreiben Sie diese Methode, um die Hintergrundfarbe der Befehle in einem Popupmenü ändern.  
  
##  <a name="a-nameonsizea--cframewndexonsize"></a><a name="onsize"></a>CFrameWndEx::OnSize  
 Vom Framework aufgerufen, nachdem ändert sich der Frame.  
  
```  
afx_msg void OnSize(
    UINT nType,  
    int cx,  
    int cy);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nType`  
 Der Typ der Größe ändern. Mögliche Werte finden Sie in den Parameter `wParam` in [WM_SIZE Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms632646).  
  
 [in] `cx`  
 Neue Breite des Rahmens in Pixel.  
  
 [in] `cy`  
 Neue Höhe des Rahmens in Pixel.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonsizinga--cframewndexonsizing"></a><a name="onsizing"></a>CFrameWndEx::OnSizing  
 Wird vom Framework aufgerufen, wenn der Benutzer den Frame ändert.  
  
```  
afx_msg void OnSizing(
    UINT fwSide,  
    LPRECT pRect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `fwSide`  
 Der Rand des Rahmens, die verschoben werden. Der Parameter `wParam` in [WM_SIZING Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms632647).  
  
 [in, out] `pRect`  
 Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) oder [RECT](../../mfc/reference/rect-structure1.md) -Struktur, die die Frame-Koordinaten enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonsyscolorchangea--cframewndexonsyscolorchange"></a><a name="onsyscolorchange"></a>CFrameWndEx::OnSysColorChange  
 Vom Framework aufgerufen, wenn sich die Systemfarben ändern.  
  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameontearoffmenua--cframewndexontearoffmenu"></a><a name="ontearoffmenu"></a>CFrameWndEx::OnTearOffMenu  
 Vom Framework aufgerufen, wenn die Anwendung ein Menü angezeigt wird, die ein positionierbar wird.  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenuPopup`  
 Ein Zeiger auf ein Popup-Menü.  
  
 [in] `pBar`  
 Ein Zeiger auf einen Balken abtrennbare.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Popupmenü mit der Leiste abtrennbare aktiviert ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, benutzerdefinierten Code auszuführen, wenn das Framework eine Steuerleiste angezeigt.  
  
 Die standardmäßige Implementierung keine Aktion aus und gibt `TRUE`.  
  
##  <a name="a-nameontoolbarcontextmenua--cframewndexontoolbarcontextmenu"></a><a name="ontoolbarcontextmenu"></a>CFrameWndEx::OnToolbarContextMenu  
 Aufgerufen, um ein Popupmenü der Symbolleiste zu erstellen.  
  
```  
afx_msg LRESULT OnToolbarContextMenu(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wp`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `lp`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameontoolbarcreatenewa--cframewndexontoolbarcreatenew"></a><a name="ontoolbarcreatenew"></a>CFrameWndEx::OnToolbarCreateNew  
 Das Framework ruft diese Methode, um eine neue Symbolleiste zu erstellen.  
  
```  
afx_msg LRESULT OnToolbarCreateNew(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wp`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `lp`  
 Zeiger auf den Text für die Titelleiste der Symbolleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die neue Symbolleiste. oder `NULL` eine Symbolleiste nicht erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameontoolbardeletea--cframewndexontoolbardelete"></a><a name="ontoolbardelete"></a>CFrameWndEx::OnToolbarDelete  
 Wird vom Framework aufgerufen, wenn eine Symbolleiste gelöscht wird.  
  
```  
afx_msg LRESULT OnToolbarDelete(
    WPARAM, 
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parameter  
 [in]  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `lp`  
 Ein Zeiger auf eine Symbolleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Symbolleiste gelöscht wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonupdateframemenua--cframewndexonupdateframemenu"></a><a name="onupdateframemenu"></a>CFrameWndEx::OnUpdateFrameMenu  
 Aufgerufen, klicken Sie im Frame fest.  
  
```  
virtual void OnUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMenuAlt`  
 Handle für den alternativen Menüs.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonupdateframetitlea--cframewndexonupdateframetitle"></a><a name="onupdateframetitle"></a>CFrameWndEx::OnUpdateFrameTitle  
 Das Framework ruft diese Methode, um die Titelleiste des Rahmenfensters.  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAddToTitle`  
 `TRUE`So fügen Sie den Titel des aktiven Dokuments auf die Titelleiste der Frame-Fensters; andernfalls`FALSE.`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonupdatepanemenua--cframewndexonupdatepanemenu"></a><a name="onupdatepanemenu"></a>CFrameWndEx::OnUpdatePaneMenu  
 Vom Framework aufgerufen wird, klicken Sie im Bereich zu aktualisieren.  
  
```  
afx_msg void OnUpdatePaneMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pCmdUI`  
 Ein Zeiger auf das Benutzeroberflächenobjekt Bereich.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonwindowposchangeda--cframewndexonwindowposchanged"></a><a name="onwindowposchanged"></a>CFrameWndEx::OnWindowPosChanged  
 Wird vom Framework aufgerufen, wenn die Größe, Position oder Z-Reihenfolge wegen eines Aufrufs einer Verwaltungsmethode Fenster geändert hat.  
  
```  
afx_msg void OnWindowPosChanged(WINDOWPOS FAR* lpwndpos);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpwndpos`  
 Zeiger auf eine [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) Struktur, die die neue Größe und Position enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namepanefrompointa--cframewndexpanefrompoint"></a><a name="panefrompoint"></a>CFrameWndEx::PaneFromPoint  
 Sucht nach jedem Bereich für den angegebenen Punkt.  
  
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
 Die Bildschirmkoordinaten des Punkts zu überprüfen.  
  
 [in] `nSensitivity`  
 Erweitern Sie das umschließende Rechteck jedes Steuerleiste um diesen Betrag, bei der Suche nach Punkt.  
  
 [in] `bExactBar`  
 `TRUE`ignoriert die `nSensitivity` Parameter ist, andernfalls `FALSE`.  
  
 [in] `pRTCBarType`  
 Wenn dies nicht `NULL`, sucht die Methode nur die Steuerleisten des angegebenen Typs.  
  
 [out] `dwAlignment`  
 Wenn erfolgreich, enthält dieser Parameter den Rand der Steuerleiste, die dem angegebenen Punkt am nächsten ist. Andernfalls ist dieser Parameter nicht initialisiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Steuerleiste, die enthält die `point`; `NULL` , wenn kein Steuerelement gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sucht die Steuerleisten in der Anwendung für eine `point`.  
  
 Verwendung `nSensitivity` um den Suchbereich zu vergrößern. Verwendung `pRTCBarType` Steuerleisten Benutzertypen, die die Methode sucht.  
  
##  <a name="a-namepretranslatemessagea--cframewndexpretranslatemessage"></a><a name="pretranslatemessage"></a>CFrameWndEx::PreTranslateMessage  
 Bestimmte Windows-Meldungen verarbeitet, bevor sie verteilt wurden.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMsg`  
 Ein Zeiger auf eine [MSG](../../mfc/reference/msg-structure1.md) Struktur, die die zu verarbeitende Meldung enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Meldung behandelt wurde und nicht weitergeleitet werden soll; 0, wenn die Nachricht nicht verarbeitet wurde und weitergeleitet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namerecalclayouta--cframewndexrecalclayout"></a><a name="recalclayout"></a>CFrameWndEx::RecalcLayout  
 Passt das Layout des Rahmens und zugehöriges untergeordnetes Fenster.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bNotify`  
 Gibt an, ob das OLE-Clientelement über die layoutänderung benachrichtigen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn die Größe des Rahmenfensters geändert hat oder Wenn Steuerleisten angezeigt oder ausgeblendet werden.  
  
##  <a name="a-nameremovepanefromdockmanagera--cframewndexremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CFrameWndEx::RemovePaneFromDockManager  
 Hebt die Registrierung eines Bereichs, und entfernt sie aus der Dockingstation-Manager.  
  
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
 Ein Zeiger auf die Steuerelement-Leistenbereich zu entfernen.  
  
 [in] `bDestroy`  
 `TRUE`um die Steuerleiste zu zerstören, nach dem Entfernen; `FALSE` andernfalls.  
  
 [in] `bAdjustLayout`  
 `TRUE`das Andocken Layout anpassen; `FALSE` andernfalls.  
  
 [in] `bAutoHide`  
 `TRUE`Wenn die Steuerleiste in automatisch ausgeblendet ist. `FALSE` andernfalls.  
  
 [in] `pBarReplacement`  
 Ein Zeiger auf einen Bereich, der Bereich entfernten ersetzt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Steuerleiste aus der Dockingstation Layout des Rahmenfensters zu entfernen.  
  
 Die [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) behandelt das Layout von Steuerleisten. Sie müssen jede Steuerleiste docking-Manager registrieren, indem die [CFrameWndEx::AddPane](#addpane) Methode oder die [CFrameWndEx::InsertPane](#insertpane) Methode.  
  
##  <a name="a-namesetdockstatea--cframewndexsetdockstate"></a><a name="setdockstate"></a>CFrameWndEx::SetDockState  
 Stellt wieder her, das Andocken Layout Andocken in der Registrierung gespeichert.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Parameter  
 `state`  
 Der Andockstatus. Dieser Parameter wird ignoriert.  
  
##  <a name="a-namesetprintpreviewframea--cframewndexsetprintpreviewframe"></a><a name="setprintpreviewframe"></a>CFrameWndEx::SetPrintPreviewFrame  
 Legt das Rahmenfenster Seitenansicht.  
  
```  
void SetPrintPreviewFrame(CFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf ein Rahmenfenster Seitenansicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetuptoolbarmenua--cframewndexsetuptoolbarmenu"></a><a name="setuptoolbarmenu"></a>CFrameWndEx::SetupToolbarMenu  
 Fügt eine benutzerdefinierte Befehle in einem Symbolleistenmenü.  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `menu`  
 Ein `CMenu` Objekt geändert werden.  
  
 [in] `uiViewUserToolbarCmdFirst`  
 Mit dem ersten benutzerdefinierten Befehl.  
  
 [in] `uiViewUserToolbarCmdLast`  
 Der letzte benutzerdefinierte Befehl.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework speichert benutzerdefinierte Befehle in einer Liste. Verwendung `uiViewUserToolbarCmdFirst` und `uiViewUserToolbarCmdList` die Indizes der Befehle zum Einfügen an.  
  
##  <a name="a-nameshowfullscreena--cframewndexshowfullscreen"></a><a name="showfullscreen"></a>CFrameWndEx::ShowFullScreen  
 Schaltet den Hauptframe zwischen dem Vollbildmodus und dem normalen Modus.  
  
```  
void ShowFullScreen();
```  
  
##  <a name="a-nameshowpanea--cframewndexshowpane"></a><a name="showpane"></a>CFrameWndEx::ShowPane  
 Anzeigen oder ausblenden im angegebenen Bereich.  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf die Steuerleiste ein- oder ausblenden.  
  
 [in] `bShow`  
 Wenn `TRUE`, die Anwendung zeigt die Steuerleiste. Andernfalls wird die Anwendung die Steuerleiste ausgeblendet.  
  
 [in] `bDelay`  
 Wenn `TRUE`, die Anpassung des andocklayouts zu verzögern, bis das Framework ruft [CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout). Andernfalls neu berechnen Sie sofort die andocklayouts.  
  
 [in] `bActivate`  
 Wenn `TRUE`, damit die Steuerleiste aktiviert. Andernfalls werden die Steuerleiste in einen inaktiven Status angezeigt.  
  
##  <a name="a-nameupdatecaptiona--cframewndexupdatecaption"></a><a name="updatecaption"></a>CFrameWndEx::UpdateCaption  
 Aufgerufen, um die Beschriftung des Fensters Frame zu aktualisieren.  
  
```  
void UpdateCaption();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namewinhelpa--cframewndexwinhelp"></a><a name="winhelp"></a>CFrameWndEx::WinHelp  
 Ruft die WinHelp-Anwendung oder das Kontextmenü Hilfe beziehen.  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Parameter  
 `dwData`  
 Daten, die hängt die `nCmd` Parameter. Eine Liste der möglichen Werte finden Sie unter [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267).  
  
 `nCmd`  
 Der Help-Befehl. Eine Liste der möglichen Werte finden Sie unter [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267).  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)

