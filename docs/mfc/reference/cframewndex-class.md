---
title: CFrameWndEx Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFrameWndEx
- AFXFRAMEWNDEX/CFrameWndEx
- AFXFRAMEWNDEX/CFrameWndEx::ActiveItemRecalcLayout
- AFXFRAMEWNDEX/CFrameWndEx::AddPane
- AFXFRAMEWNDEX/CFrameWndEx::AdjustDockingLayout
- AFXFRAMEWNDEX/CFrameWndEx::DelayUpdateFrameMenu
- AFXFRAMEWNDEX/CFrameWndEx::DockPane
- AFXFRAMEWNDEX/CFrameWndEx::DockPaneLeftOf
- AFXFRAMEWNDEX/CFrameWndEx::EnableAutoHidePanes
- AFXFRAMEWNDEX/CFrameWndEx::EnableDocking
- AFXFRAMEWNDEX/CFrameWndEx::EnableFullScreenMainMenu
- AFXFRAMEWNDEX/CFrameWndEx::EnableFullScreenMode
- AFXFRAMEWNDEX/CFrameWndEx::EnableLoadDockState
- AFXFRAMEWNDEX/CFrameWndEx::EnablePaneMenu
- AFXFRAMEWNDEX/CFrameWndEx::GetActivePopup
- AFXFRAMEWNDEX/CFrameWndEx::GetDefaultResId
- AFXFRAMEWNDEX/CFrameWndEx::GetDockingManager
- AFXFRAMEWNDEX/CFrameWndEx::GetMenuBar
- AFXFRAMEWNDEX/CFrameWndEx::GetPane
- AFXFRAMEWNDEX/CFrameWndEx::GetRibbonBar
- AFXFRAMEWNDEX/CFrameWndEx::GetTearOffBars
- AFXFRAMEWNDEX/CFrameWndEx::GetToolbarButtonToolTipText
- AFXFRAMEWNDEX/CFrameWndEx::InsertPane
- AFXFRAMEWNDEX/CFrameWndEx::IsFullScreen
- AFXFRAMEWNDEX/CFrameWndEx::IsMenuBarAvailable
- AFXFRAMEWNDEX/CFrameWndEx::IsPointNearDockSite
- AFXFRAMEWNDEX/CFrameWndEx::IsPrintPreview
- AFXFRAMEWNDEX/CFrameWndEx::LoadFrame
- AFXFRAMEWNDEX/CFrameWndEx::NegotiateBorderSpace
- AFXFRAMEWNDEX/CFrameWndEx::OnActivate
- AFXFRAMEWNDEX/CFrameWndEx::OnActivateApp
- AFXFRAMEWNDEX/CFrameWndEx::OnChangeVisualManager
- AFXFRAMEWNDEX/CFrameWndEx::OnClose
- AFXFRAMEWNDEX/CFrameWndEx::OnCloseDockingPane
- AFXFRAMEWNDEX/CFrameWndEx::OnCloseMiniFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnClosePopupMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnCmdMsg
- AFXFRAMEWNDEX/CFrameWndEx::OnContextHelp
- AFXFRAMEWNDEX/CFrameWndEx::OnCreate
- AFXFRAMEWNDEX/CFrameWndEx::OnDestroy
- AFXFRAMEWNDEX/CFrameWndEx::OnDrawMenuImage
- AFXFRAMEWNDEX/CFrameWndEx::OnDrawMenuLogo
- AFXFRAMEWNDEX/CFrameWndEx::OnDWMCompositionChanged
- AFXFRAMEWNDEX/CFrameWndEx::OnExitSizeMove
- AFXFRAMEWNDEX/CFrameWndEx::OnGetMinMaxInfo
- AFXFRAMEWNDEX/CFrameWndEx::OnIdleUpdateCmdUI
- AFXFRAMEWNDEX/CFrameWndEx::OnLButtonDown
- AFXFRAMEWNDEX/CFrameWndEx::OnLButtonUp
- AFXFRAMEWNDEX/CFrameWndEx::OnMenuButtonToolHitTest
- AFXFRAMEWNDEX/CFrameWndEx::OnMenuChar
- AFXFRAMEWNDEX/CFrameWndEx::OnMouseMove
- AFXFRAMEWNDEX/CFrameWndEx::OnMoveMiniFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnNcActivate
- AFXFRAMEWNDEX/CFrameWndEx::OnNcCalcSize
- AFXFRAMEWNDEX/CFrameWndEx::OnNcHitTest
- AFXFRAMEWNDEX/CFrameWndEx::OnNcMouseMove
- AFXFRAMEWNDEX/CFrameWndEx::OnNcPaint
- AFXFRAMEWNDEX/CFrameWndEx::OnPaneCheck
- AFXFRAMEWNDEX/CFrameWndEx::OnPostPreviewFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnPowerBroadcast
- AFXFRAMEWNDEX/CFrameWndEx::OnSetMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnSetPreviewMode
- AFXFRAMEWNDEX/CFrameWndEx::OnSetText
- AFXFRAMEWNDEX/CFrameWndEx::OnShowCustomizePane
- AFXFRAMEWNDEX/CFrameWndEx::OnShowPanes
- AFXFRAMEWNDEX/CFrameWndEx::OnShowPopupMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnSize
- AFXFRAMEWNDEX/CFrameWndEx::OnSizing
- AFXFRAMEWNDEX/CFrameWndEx::OnSysColorChange
- AFXFRAMEWNDEX/CFrameWndEx::OnTearOffMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarContextMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarCreateNew
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarDelete
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdateFrameMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdateFrameTitle
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdatePaneMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnWindowPosChanged
- AFXFRAMEWNDEX/CFrameWndEx::PaneFromPoint
- AFXFRAMEWNDEX/CFrameWndEx::PreTranslateMessage
- AFXFRAMEWNDEX/CFrameWndEx::RecalcLayout
- AFXFRAMEWNDEX/CFrameWndEx::RemovePaneFromDockManager
- AFXFRAMEWNDEX/CFrameWndEx::SetDockState
- AFXFRAMEWNDEX/CFrameWndEx::SetPrintPreviewFrame
- AFXFRAMEWNDEX/CFrameWndEx::SetupToolbarMenu
- AFXFRAMEWNDEX/CFrameWndEx::ShowFullScreen
- AFXFRAMEWNDEX/CFrameWndEx::ShowPane
- AFXFRAMEWNDEX/CFrameWndEx::UpdateCaption
- AFXFRAMEWNDEX/CFrameWndEx::WinHelp
dev_langs: C++
helpviewer_keywords:
- CFrameWndEx [MFC], ActiveItemRecalcLayout
- CFrameWndEx [MFC], AddPane
- CFrameWndEx [MFC], AdjustDockingLayout
- CFrameWndEx [MFC], DelayUpdateFrameMenu
- CFrameWndEx [MFC], DockPane
- CFrameWndEx [MFC], DockPaneLeftOf
- CFrameWndEx [MFC], EnableAutoHidePanes
- CFrameWndEx [MFC], EnableDocking
- CFrameWndEx [MFC], EnableFullScreenMainMenu
- CFrameWndEx [MFC], EnableFullScreenMode
- CFrameWndEx [MFC], EnableLoadDockState
- CFrameWndEx [MFC], EnablePaneMenu
- CFrameWndEx [MFC], GetActivePopup
- CFrameWndEx [MFC], GetDefaultResId
- CFrameWndEx [MFC], GetDockingManager
- CFrameWndEx [MFC], GetMenuBar
- CFrameWndEx [MFC], GetPane
- CFrameWndEx [MFC], GetRibbonBar
- CFrameWndEx [MFC], GetTearOffBars
- CFrameWndEx [MFC], GetToolbarButtonToolTipText
- CFrameWndEx [MFC], InsertPane
- CFrameWndEx [MFC], IsFullScreen
- CFrameWndEx [MFC], IsMenuBarAvailable
- CFrameWndEx [MFC], IsPointNearDockSite
- CFrameWndEx [MFC], IsPrintPreview
- CFrameWndEx [MFC], LoadFrame
- CFrameWndEx [MFC], NegotiateBorderSpace
- CFrameWndEx [MFC], OnActivate
- CFrameWndEx [MFC], OnActivateApp
- CFrameWndEx [MFC], OnChangeVisualManager
- CFrameWndEx [MFC], OnClose
- CFrameWndEx [MFC], OnCloseDockingPane
- CFrameWndEx [MFC], OnCloseMiniFrame
- CFrameWndEx [MFC], OnClosePopupMenu
- CFrameWndEx [MFC], OnCmdMsg
- CFrameWndEx [MFC], OnContextHelp
- CFrameWndEx [MFC], OnCreate
- CFrameWndEx [MFC], OnDestroy
- CFrameWndEx [MFC], OnDrawMenuImage
- CFrameWndEx [MFC], OnDrawMenuLogo
- CFrameWndEx [MFC], OnDWMCompositionChanged
- CFrameWndEx [MFC], OnExitSizeMove
- CFrameWndEx [MFC], OnGetMinMaxInfo
- CFrameWndEx [MFC], OnIdleUpdateCmdUI
- CFrameWndEx [MFC], OnLButtonDown
- CFrameWndEx [MFC], OnLButtonUp
- CFrameWndEx [MFC], OnMenuButtonToolHitTest
- CFrameWndEx [MFC], OnMenuChar
- CFrameWndEx [MFC], OnMouseMove
- CFrameWndEx [MFC], OnMoveMiniFrame
- CFrameWndEx [MFC], OnNcActivate
- CFrameWndEx [MFC], OnNcCalcSize
- CFrameWndEx [MFC], OnNcHitTest
- CFrameWndEx [MFC], OnNcMouseMove
- CFrameWndEx [MFC], OnNcPaint
- CFrameWndEx [MFC], OnPaneCheck
- CFrameWndEx [MFC], OnPostPreviewFrame
- CFrameWndEx [MFC], OnPowerBroadcast
- CFrameWndEx [MFC], OnSetMenu
- CFrameWndEx [MFC], OnSetPreviewMode
- CFrameWndEx [MFC], OnSetText
- CFrameWndEx [MFC], OnShowCustomizePane
- CFrameWndEx [MFC], OnShowPanes
- CFrameWndEx [MFC], OnShowPopupMenu
- CFrameWndEx [MFC], OnSize
- CFrameWndEx [MFC], OnSizing
- CFrameWndEx [MFC], OnSysColorChange
- CFrameWndEx [MFC], OnTearOffMenu
- CFrameWndEx [MFC], OnToolbarContextMenu
- CFrameWndEx [MFC], OnToolbarCreateNew
- CFrameWndEx [MFC], OnToolbarDelete
- CFrameWndEx [MFC], OnUpdateFrameMenu
- CFrameWndEx [MFC], OnUpdateFrameTitle
- CFrameWndEx [MFC], OnUpdatePaneMenu
- CFrameWndEx [MFC], OnWindowPosChanged
- CFrameWndEx [MFC], PaneFromPoint
- CFrameWndEx [MFC], PreTranslateMessage
- CFrameWndEx [MFC], RecalcLayout
- CFrameWndEx [MFC], RemovePaneFromDockManager
- CFrameWndEx [MFC], SetDockState
- CFrameWndEx [MFC], SetPrintPreviewFrame
- CFrameWndEx [MFC], SetupToolbarMenu
- CFrameWndEx [MFC], ShowFullScreen
- CFrameWndEx [MFC], ShowPane
- CFrameWndEx [MFC], UpdateCaption
- CFrameWndEx [MFC], WinHelp
ms.assetid: 5830aca8-4a21-4f31-91f1-dd5477ffcc8d
caps.latest.revision: "39"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b968985c598dafe2ed96295c7388d650dc18c636
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cframewndex-class"></a>CFrameWndEx-Klasse
Implementiert die Funktionalität eines Windows-SDI-Rahmenfensters (Single Document Interface), wobei es sich um ein überlappendes oder ein Popupfenster handeln kann. Ebenfalls bereitgestellt werden Member zum Verwalten des Fensters. Es erweitert die [CFrameWnd](../../mfc/reference/cframewnd-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFrameWndEx::ActiveItemRecalcLayout](#activeitemrecalclayout)|Passt das Layout der OLE-Clientelement und Clientbereich des Frames.|  
|`CFrameWndEx::AddDockSite`|Diese Methode wird nicht verwendet.|  
|[CFrameWndEx::AddPane](#addpane)|Registriert eine Steuerleiste beim Dock-Manager.|  
|[CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)|Berechnet das Layout von allen Bereichen, die die Frame-Fensters angedockt sind.|  
|[CFrameWndEx::DelayUpdateFrameMenu](#delayupdateframemenu)|Legt die Frame-Menü und wird aktualisiert, wenn befehlsverarbeitung im Leerlauf befindet.|  
|[CFrameWndEx::DockPane](#dockpane)|Dockt den angegebenen Bereich an das Rahmenfenster an.|  
|[CFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.|  
|[CFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)|Können den automatischen Ausblendemodus für die Bereiche aus, wenn sie sich an den angegebenen Seiten des Hauptrahmenfenster angedockt sind.|  
|[Cframewndex:: EnableDocking](#enabledocking)|Ermöglicht das Andocken der Bereiche, die zum Rahmenfenster gehören.|  
|[CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)|Anzeigen oder ausblenden im Hauptmenü in einem Vollbildmodus.|  
|[CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode)|Ermöglicht den Vollbildmodus für das Rahmenfenster.|  
|[CFrameWndEx::EnableLoadDockState](#enableloaddockstate)|Aktiviert oder deaktiviert das Laden von den andockzustand.|  
|[CFrameWndEx::EnablePaneMenu](#enablepanemenu)|Aktiviert oder deaktiviert die automatische Behandlung von klicken Sie im Bereich.|  
|[CFrameWndEx::GetActivePopup](#getactivepopup)|Gibt einen Zeiger auf das aktuell angezeigte Popupmenü zurück.|  
|[CFrameWndEx::GetDefaultResId](#getdefaultresid)|Gibt die Ressourcen-ID, die Sie angegeben werden, wenn das Framework das Rahmenfenster geladen.|  
|[CFrameWndEx::GetDockingManager](#getdockingmanager)|Ruft die [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) Objekt für das Rahmenfenster.|  
|[CFrameWndEx::GetMenuBar](#getmenubar)|Gibt einen Zeiger auf das Menüleistenobjekt zurück, das an das Rahmenfenster angefügt ist.|  
|[CFrameWndEx::GetPane](#getpane)|Gibt einen Zeiger auf den Bereich, der die angegebene ID verfügt.|  
|[CFrameWndEx::GetRibbonBar](#getribbonbar)|Ruft das Menübandsteuerelement für den Frame ab.|  
|[CFrameWndEx::GetTearOffBars](#gettearoffbars)|Gibt eine Liste von Bereichsobjekten zurück, die sich in einem abtrennbaren Zustand befinden.|  
|[CFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Vom Framework aufgerufen, wenn die Anwendung zeigt die QuickInfo für eine Symbolleisten-Schaltfläche an.|  
|[CFrameWndEx::InsertPane](#insertpane)|Registriert einen Bereich beim Dock-Manager.|  
|[CFrameWndEx::IsFullScreen](#isfullscreen)|Bestimmt, ob das Rahmenfenster im Vollbildmodus.|  
|[CFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|Bestimmt, ob der Zeiger auf das menüleistenobjekt gültig ist.|  
|[CFrameWndEx::IsPointNearDockSite](#ispointneardocksite)|Gibt an, ob der Punkt in einer Zone Ausrichtung sind.|  
|[CFrameWndEx::IsPrintPreview](#isprintpreview)|Gibt an, ob das Rahmenfenster im Seitenansichtsmodus ist.|  
|[CFrameWndEx::LoadFrame](#loadframe)|Diese Methode wird aufgerufen, nachdem Konstruktion So erstellen das Rahmenfenster und Laden ihre Ressourcen.|  
|[CFrameWndEx::NegotiateBorderSpace](#negotiateborderspace)|Implementiert OLE-Client-Border-Aushandlung.|  
|[CFrameWndEx::OnActivate](#onactivate)|Das Framework ruft diese Methode auf, wenn Benutzereingaben zu oder von den Frame gewechselt wird.|  
|[CFrameWndEx::OnActivateApp](#onactivateapp)|Vom Framework aufgerufen, wenn die Anwendung aktiviert oder deaktiviert ist.|  
|[CFrameWndEx::OnChangeVisualManager](#onchangevisualmanager)|Vom Framework aufgerufen, wenn eine Änderung des Frames, eine Änderung an der visuellen Manager erforderlich ist.|  
|[CFrameWndEx::OnClose](#onclose)|Das Framework ruft diese Methode, um den Frame zu schließen.|  
|[CFrameWndEx::OnCloseDockingPane](#onclosedockingpane)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **schließen** auf einen andockbaren Bereich auf die Schaltfläche.|  
|[CFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **schließen** Schaltfläche auf einem schwebenden Mini Rahmenfenster.|  
|[CFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|Wird vom Framework aufgerufen, wenn ein aktives Popupmenü eine WM_DESTROY-Meldung verarbeitet.|  
|[CFrameWndEx::OnCmdMsg](#oncmdmsg)|Sendet Nachrichten-Befehl.|  
|[CFrameWndEx::OnContextHelp](#oncontexthelp)|Vom Framework aufgerufen, Hilfe, zum Anzeigen von Kontext beziehen.|  
|[CFrameWndEx::OnCreate](#oncreate)|Vom Framework aufgerufen, nachdem der Rahmen erstellt wird.|  
|[CFrameWndEx::OnDestroy](#ondestroy)|Vom Framework aufgerufen, wenn der Frame zerstört wird.|  
|[CFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|Vom Framework aufgerufen, wenn die Anwendung das Bild, die einem Menüeelement zugeordneten Webseiteninhalte zeichnet.|  
|[CFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|Vom Framework aufgerufen, wenn eine `CMFCPopupMenu` -Objekt Prozesse eine [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Nachricht.|  
|[CFrameWndEx::OnDWMCompositionChanged](#ondwmcompositionchanged)|Wird vom Framework aufgerufen, wenn es sich bei Desktop-Desktopfenster-Manager (DWM) Komposition aktiviert oder deaktiviert wurde.|  
|[CFrameWndEx::OnExitSizeMove](#onexitsizemove)|Vom Framework aufgerufen, wenn der Frame beendet wird, verschieben oder Ändern der Größe.|  
|[CFrameWndEx::OnGetMinMaxInfo](#ongetminmaxinfo)|Wird vom Framework aufgerufen, wenn es sich bei der Frame Fenster Dimension begrenzen angepasst wird.|  
|[CFrameWndEx::OnIdleUpdateCmdUI](#onidleupdatecmdui)|Vom Framework aufgerufen, die die Frame-Anzeige zu aktualisieren, wenn befehlsverarbeitung im Leerlauf befindet.|  
|[CFrameWndEx::OnLButtonDown](#onlbuttondown)|Das Framework ruft diese Methode auf, wenn der Benutzer die linke Maustaste drückt.|  
|[CFrameWndEx::OnLButtonUp](#onlbuttonup)|Das Framework ruft diese Methode auf, wenn der Benutzer die linke Maustaste loslässt.|  
|[CFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|Vom Framework aufgerufen, wenn eine `CMFCToolBarButton` -Objekt Prozesse eine `WM_NCHITTEST` Nachricht.|  
|[CFrameWndEx::OnMenuChar](#onmenuchar)|Vom Framework aufgerufen, wenn ein Menü angezeigt wird und der Benutzer drückt einen Schlüssel, der nicht an einen Befehl entsprechen.|  
|[CFrameWndEx::OnMouseMove](#onmousemove)|Das Framework ruft diese Methode auf, wenn der Mauszeiger bewegt wird.|  
|[CFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)|Vom Framework aufgerufen, wenn ein Fenster verschoben wird.|  
|[CFrameWndEx::OnNcActivate](#onncactivate)|Vom Framework aufgerufen, wenn der nicht-Clientbereich des Frames neu gezeichnet werden muss, um eine Änderung im aktiven Zustand anzuzeigen.|  
|[CFrameWndEx::OnNcCalcSize](#onnccalcsize)|Vom Framework aufgerufen, wenn die Größe und Position des Clientbereichs berechnet werden müssen.|  
|[CFrameWndEx::OnNcHitTest](#onnchittest)|Wird vom Framework aufgerufen, wenn der Mauszeiger bewegt wird, oder wenn eine Maustaste gedrückt oder losgelassen wird.|  
|[CFrameWndEx::OnNcMouseMove](#onncmousemove)|Vom Framework aufgerufen, wenn der Mauszeiger in einem clientfremden Bereich.|  
|[CFrameWndEx::OnNcPaint](#onncpaint)|Vom Framework aufgerufen, wenn der nicht-Clientbereichs gezeichnet werden muss.|  
|[CFrameWndEx::OnPaneCheck](#onpanecheck)|Wird aufgerufen, durch das Framework, um die Sichtbarkeit eines Bereichs steuern.|  
|[CFrameWndEx::OnPostPreviewFrame](#onpostpreviewframe)|Vom Framework aufgerufen, wenn der Benutzer die Seitenansicht geändert wurde.|  
|[CFrameWndEx::OnPowerBroadcast](#onpowerbroadcast)|Vom Framework aufgerufen, wenn ein Power Management-Ereignis auftritt.|  
|[CFrameWndEx::OnSetMenu](#onsetmenu)|Wird aufgerufen, durch das Framework das Fenstermenü Frame zu ersetzen.|  
|[CFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|Wird aufgerufen, durch das Framework für den Rahmen der Seitenansicht festgelegt.|  
|[CFrameWndEx::OnSetText](#onsettext)|Vom Framework aufgerufen wird, legen Sie den Text eines Fensters.|  
|[CFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)|Vom Framework aufgerufen, wenn eine schnelle anpassen Bereich aktiviert ist.|  
|[CFrameWndEx::OnShowPanes](#onshowpanes)|Vom Framework aufgerufen, ein- oder Ausblenden von Bereichen.|  
|[CFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|Vom Framework aufgerufen, wenn ein Popupmenü aktiviert ist.|  
|[CFrameWndEx::OnSize](#onsize)|Das Framework ruft diese Methode nach den Frame Fenstergröße ändert.|  
|[CFrameWndEx::OnSizing](#onsizing)|Das Framework ruft diese Methode auf, wenn der Benutzer die Größe den Rahmen ändern.|  
|[CFrameWndEx::OnSysColorChange](#onsyscolorchange)|Wird vom Framework aufgerufen, wenn sich die Systemfarben ändern.|  
|[CFrameWndEx::OnTearOffMenu](#ontearoffmenu)|Vom Framework aufgerufen, wenn ein Menü, das eine abtrennbarer Leiste aktiviert ist.|  
|[CFrameWndEx::OnToolbarContextMenu](#ontoolbarcontextmenu)|Wird aufgerufen, durch das Framework zum Erstellen einer Symbolleiste-Kontextmenü.|  
|[CFrameWndEx::OnToolbarCreateNew](#ontoolbarcreatenew)|Das Framework ruft diese Methode, um eine neue Symbolleiste zu erstellen.|  
|[CFrameWndEx::OnToolbarDelete](#ontoolbardelete)|Vom Framework aufgerufen, wenn eine Symbolleiste gelöscht wird.|  
|[CFrameWndEx::OnUpdateFrameMenu](#onupdateframemenu)|Vom Framework aufgerufen wird, klicken Sie im Frame festgelegt.|  
|[CFrameWndEx::OnUpdateFrameTitle](#onupdateframetitle)|Das Framework ruft diese Methode, um die Titelleiste des Rahmenfensters zu aktualisieren.|  
|[CFrameWndEx::OnUpdatePaneMenu](#onupdatepanemenu)|Vom Framework aufgerufen wird, klicken Sie im Bereich zu aktualisieren.|  
|[CFrameWndEx::OnWindowPosChanged](#onwindowposchanged)|Vom Framework aufgerufen, wenn die Größe, Position oder Z-Reihenfolge wegen eines Aufrufs einer Verwaltungsmethode Fenster geändert wurde.|  
|[CFrameWndEx::PaneFromPoint](#panefrompoint)|Gibt die andockbaren Bereich, der den angegebenen Punkt enthält.|  
|[CFrameWndEx::PreTranslateMessage](#pretranslatemessage)|Bestimmte Windows-Meldungen verarbeitet, bevor sie verteilt wurden.|  
|[CFrameWndEx::RecalcLayout](#recalclayout)|Passt das Layout des Frames und zugehöriges untergeordnetes Fenster.|  
|[CFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|Hebt die Registrierung auf einen Bereich, und entfernt sie aus der internen Liste in Dock-Manager.|  
|[CFrameWndEx::SetDockState](#setdockstate)|Stellt den andockzustand in der Registrierung gespeicherten am Layout des Docks wieder her.|  
|[CFrameWndEx::SetPrintPreviewFrame](#setprintpreviewframe)|Legt das Rahmenfenster Seitenansicht zu blättern.|  
|[CFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|Fügt eine benutzerdefinierte Befehle in einem Symbolleistenmenüs.|  
|[CFrameWndEx::ShowFullScreen](#showfullscreen)|Schaltet den Hauptframe zwischen den gesamten Bildschirm und die regulären Modi.|  
|[CFrameWndEx::ShowPane](#showpane)|Zeigt an oder blendet Sie aus dem angegebenen Bereich.|  
|[CFrameWndEx::UpdateCaption](#updatecaption)|Wird aufgerufen, durch das Framework die framebeschriftung Fenster zu aktualisieren.|  
|[CFrameWndEx::WinHelp](#winhelp)|Wird aufgerufen, entweder die `WinHelp` Anwendung oder das Kontextmenü im Zusammenhang Hilfe.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine Klasse von erben die `CFrameWndEx` Klasse. Das Beispiel veranschaulicht die Methodensignaturen in der Unterklasse und das Überschreiben der `OnShowPopupMenu` Methode. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#3](../../mfc/reference/codesnippet/cpp/cframewndex-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#4](../../mfc/reference/codesnippet/cpp/cframewndex-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CFrameWndEx](../../mfc/reference/cframewndex-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxframewndex.h  
  
##  <a name="activeitemrecalclayout"></a>CFrameWndEx::ActiveItemRecalcLayout  
 Passt das Layout der OLE-Clientelement und Clientbereich des Frames.  
  
```  
void ActiveItemRecalcLayout();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addpane"></a>CFrameWndEx::AddPane  
 Registriert eine Steuerleiste beim Dock-Manager.  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 Eine Steuerelement-Leistenbereich zu registrieren.  
  
 [in] `bTail`  
 `TRUE`Wenn Sie die Steuerelement-Leistenbereich bis zum Ende der Liste hinzufügen möchten; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Steuerleiste erfolgreich registriert wurde; `FALSE` andernfalls.  
  
##  <a name="adjustdockinglayout"></a>CFrameWndEx::AdjustDockingLayout  
 Berechnet das Layout von allen Bereichen, die die Frame-Fensters angedockt sind.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hdwp`  
 Ein Handle für eine Struktur, die Positionen der mehrere Fenster enthält. sein.  
  
### <a name="remarks"></a>Hinweise  
 Die Struktur Hdwp wird initialisiert, indem die [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) Methode.  
  
##  <a name="delayupdateframemenu"></a>CFrameWndEx::DelayUpdateFrameMenu  
 Legt die Frame-Menü und wird aktualisiert, wenn befehlsverarbeitung im Leerlauf befindet.  
  
```  
virtual void DelayUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMenuAlt`  
 Handle für eine alternative Menü.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="dockpane"></a>CFrameWndEx::DockPane  
 Dockt den angegebenen Bereich an das Rahmenfenster an.  
  
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
 Die ID der Seite des Rahmenfensters angedockt werden soll.  
  
 [in] `lpRect`  
 Ein Zeiger auf eine Konstante Rect-Struktur, die Bildschirmposition und die Größe des Fensters angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die `nDockBarID` Parameter kann einen der folgenden Werte aufweisen:  
  
-   AFX_IDW_DOCKBAR_TOP  
  
-   AFX_IDW_DOCKBAR_BOTTOM  
  
-   AFX_IDW_DOCKBAR_LEFT  
  
-   AFX_IDW_DOCKBAR_RIGHT  
  
##  <a name="dockpaneleftof"></a>CFrameWndEx::DockPaneLeftOf  
 Dockt den angegebenen Bereich auf der linken Seite eines anderen Bereichs an.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf das Objekt im Bereich angedockt werden.  
  
 [in] `pLeftOf`  
 Ein Zeiger auf den Bereich links neben dem Bereich gemäß Andocken `pBar`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn `pBar` erfolgreich angedockt ist. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode nimmt die Symbolleiste, die gemäß der `pBar` Parameter und wird es auf der linken Seite der Symbolleiste gemäß angedockt `pLeftOf` Parameter.  
  
##  <a name="enableautohidepanes"></a>CFrameWndEx::EnableAutoHidePanes  
 Ermöglicht das automatischen Ausblendemodus für den Bereich, wenn es an das Hauptrahmenfenster angegebenen Rand angedockt ist.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwDockStyle`  
 Gibt die Seite für das Hauptrahmenfenster, um den Bereich anzudocken.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine Leiste Bereich wird auf der Seite der Frame-Fenster, die von angegeben wird erfolgreich angedockt `dwDockStyle`, `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 `dwDockStyle`Dabei kann es sich um einen der folgenden Werte aufweisen:  
  
-   CBRS_ALIGN_TOP: ermöglicht die Steuerleiste am oberen Rand der Clientbereich eines Rahmenfensters angedockt werden.  
  
-   CBRS_ALIGN_BOTTOM: ermöglicht die Steuerleiste am unteren Rand der Clientbereich eines Rahmenfensters angedockt werden.  
  
-   CBRS_ALIGN_LEFT: ermöglicht der Steuerleiste an der linken Seite des Clientbereichs eines Frame-Fensters angedockt werden.  
  
-   CBRS_ALIGN_RIGHT: ermöglicht der Steuerleiste an der rechten Seite des Clientbereichs eines Frame-Fensters angedockt werden.  
  
##  <a name="enabledocking"></a>Cframewndex:: EnableDocking  
 Ermöglicht das Andocken der Bereiche des Rahmenfensters.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwDockStyle`  
 Gibt die Seite des Fensters Hauptframe, in denen die Leiste Bereich angedockt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine Leiste Bereich erfolgreich an der angegebenen Seite angedockt werden kann. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `dwDockStyle` Parameter kann einen der folgenden Werte aufweisen:  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="enablefullscreenmainmenu"></a>CFrameWndEx::EnableFullScreenMainMenu  
 Anzeigen oder ausblenden im Hauptmenü in einem Vollbildmodus.  
  
```  
void EnableFullScreenMainMenu(BOOL bEnableMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnableMenu`  
 `TRUE`So zeigen Sie im Hauptmenü im Vollbildmodus, an `FALSE` andernfalls.  
  
##  <a name="enablefullscreenmode"></a>CFrameWndEx::EnableFullScreenMode  
 Ermöglicht den Vollbildmodus für das Rahmenfenster.  
  
```  
void EnableFullScreenMode(UINT uiFullScreenCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiFullScreenCmd`  
 Die ID eines Befehls, die aktiviert und deaktiviert den Vollbildmodus.  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie in den Vollbildmodus alle andockbarer Steuerleisten, Symbolleisten und Menüs ausgeblendet, und die aktive Ansicht wird geändert, um den Vollbildmodus zu belegen.  
  
 Wenn Sie den Vollbildmodus aktivieren, müssen Sie eine Befehls-ID angeben, die aktiviert oder deaktiviert den Vollbildmodus. Sie können Aufrufen `EnableFullScreenMode` aus des Hauptframe `OnCreate` Funktion. Wenn ein Framefenster auf eine Vollbild-Modus wechselt, erstellt das Framework eine unverankerte Symbolleiste mit einer Schaltfläche mit der angegebenen Befehls-ID.  
  
 Wenn Sie im Hauptmenü auf dem Bildschirm angezeigt werden sollen, rufen Sie [CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu).  
  
##  <a name="enableloaddockstate"></a>CFrameWndEx::EnableLoadDockState  
 Aktiviert oder deaktiviert das Laden von den andockzustand.  
  
```  
void EnableLoadDockState(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie das Laden von den andockzustand `FALSE` um das Laden von den andockzustand zu deaktivieren.  
  
##  <a name="enablepanemenu"></a>CFrameWndEx::EnablePaneMenu  
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
 `TRUE`So aktivieren Sie die automatische Behandlung von der Steuerleiste Popupmenüs; `FALSE` So deaktivieren Sie die automatische Behandlung von der Steuerleiste Popupmenüs.  
  
 [in] `uiCustomizeCmd`  
 Die Befehls-ID, der die **anpassen** Menüelement.  
  
 [in] `strCustomizeLabel`  
 Die Bezeichnung für angezeigt werden soll die **anpassen** Menüelement  
  
 [in] `uiViewToolbarsMenuEntryID`  
 Die ID eines Menüelements Symbolleiste, die in der Steuerleiste im Popupmenü wird geöffnet.  
  
 [in] `bContextMenuShowsToolbarsOnly`  
 Wenn `TRUE`, die Steuerleiste Kontextmenü zeigt die Liste der Symbolleisten nur. Wenn `FALSE`, klicken Sie im Menü zeigt die Liste der Symbolleisten und die andockbaren Balken.  
  
 [in] `bViewMenuShowsToolbarsOnly`  
 Wenn `TRUE`, Systemmenü Balken zeigt die Liste der Symbolleisten nur. Wenn `FALSE`, klicken Sie im Menü zeigt die Liste der Symbolleisten und die andockbaren Balken.  
  
##  <a name="getactivepopup"></a>CFrameWndEx::GetActivePopup  
 Gibt einen Zeiger auf das aktuell angezeigte Popupmenü zurück.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die aktuell angezeigte Popupmenü; andernfalls `NULL`.  
  
##  <a name="getdefaultresid"></a>CFrameWndEx::GetDefaultResId  
 Gibt die Ressourcen-ID, die Sie angegeben werden, wenn das Framework das Rahmenfenster geladen.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ressourcen-ID-Wert, dass der Benutzer angegeben, wenn das Framework das Rahmenfenster geladen. 0 (null), wenn das Rahmenfenster keine Menüleiste.  
  
##  <a name="getdockingmanager"></a>CFrameWndEx::GetDockingManager  
 Ruft die [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) Objekt für das Rahmenfenster.  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Das Rahmenfenster erstellt und verwendet eine [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) Objekt, das Andocken von untergeordneten Fenster zu verwalten.  
  
##  <a name="getmenubar"></a>CFrameWndEx::GetMenuBar  
 Gibt einen Zeiger auf das Menüleistenobjekt zurück, das an das Rahmenfenster angefügt ist.  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das menüleistenobjekt an das Rahmenfenster angefügt.  
  
##  <a name="getpane"></a>CFrameWndEx::GetPane  
 Gibt einen Zeiger auf den Bereich, der die angegebene ID verfügt.  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Die Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Bereich, der die angegebene ID verfügt. `NULL`Wenn keine solchen Bereich vorhanden ist.  
  
##  <a name="getribbonbar"></a>CFrameWndEx::GetRibbonBar  
 Ruft das Menübandsteuerelement für den Frame ab.  
  
```  
CMFCRibbonBar* GetRibbonBar();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) für den Frame.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettearoffbars"></a>CFrameWndEx::GetTearOffBars  
 Gibt eine Liste von Bereichsobjekten zurück, die sich in einem abtrennbaren Zustand befinden.  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf `CObList` -Objekt, das eine Auflistung von Zeigern auf die Objekte im Bereich enthält, die in einem abtrennbare Zustand befinden.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>CFrameWndEx::GetToolbarButtonToolTipText  
 Vom Framework aufgerufen, wenn die Anwendung zeigt die QuickInfo für eine Symbolleisten-Schaltfläche an.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf eine Symbolleisten-Schaltfläche.  
  
 [in] `strTTText`  
 Der QuickInfo-Text, der für die Schaltfläche angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die QuickInfo angezeigt wurde. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Methode keine Aktion ausgeführt. Überschreiben Sie diese Methode, wenn die QuickInfo für die Symbolleisten-Schaltfläche angezeigt werden soll.  
  
##  <a name="insertpane"></a>CFrameWndEx::InsertPane  
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
 `TRUE`Wenn die Steuerleiste erfolgreich eingefügt und registriert, `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen jede Steuerleiste registrieren, indem Sie mit der [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) zu einem Layout des Docks teilnehmen.  
  
##  <a name="isfullscreen"></a>CFrameWndEx::IsFullScreen  
 Bestimmt, ob das Rahmenfenster im Vollbildmodus.  
  
```  
BOOL IsFullScreen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Rahmenfenster im Vollbildmodus ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können den Vollbildmodus festlegen, durch Aufrufen der [CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode) Methode.  
  
##  <a name="ismenubaravailable"></a>CFrameWndEx::IsMenuBarAvailable  
 Bestimmt, ob der Zeiger auf das menüleistenobjekt gültig ist.  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Rahmenfenster eine Menüleiste enthält. andernfalls `FALSE`.  
  
##  <a name="ispointneardocksite"></a>CFrameWndEx::IsPointNearDockSite  
 Bestimmt, ob der Punkt in einer Zone Ausrichtung sind.  
  
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
 Auf dem der Punkt ausgerichtet ist. Siehe die Tabelle im Abschnitt "Hinweise", um mögliche Werte.  
  
 [out] `bOuterEdge`  
 `TRUE`Wenn der Punkt in der Nähe der Framerahmen befindet; `FALSE` der Punkt in einem Clientbereich befindet.  
  
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
  
##  <a name="isprintpreview"></a>CFrameWndEx::IsPrintPreview  
 Bestimmt, ob das Rahmenfenster im Seitenansichtsmodus ist.  
  
```  
BOOL IsPrintPreview();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Rahmenfenster im Seitenansichtsmodus ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="loadframe"></a>CFrameWndEx::LoadFrame  
 Diese Methode wird aufgerufen, nachdem Konstruktion So erstellen das Rahmenfenster und Laden ihre Ressourcen.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIDResource`  
 Die Ressourcen-ID, die verwendet wird, um alle Rahmen Ressourcen geladen werden.  
  
 [in] `dwDefaultStyle`  
 Der Standard-Frame-Fensterstil.  
  
 [in] `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster des Frames.  
  
 [in] `pContext`  
 Zeiger auf eine [angegeben ist und Struktur](../../mfc/reference/ccreatecontext-structure.md) -Klasse, die vom Framework während der Erstellung der Anwendung verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn die Methode erfolgreich ausgeführt wurde, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="negotiateborderspace"></a>CFrameWndEx::NegotiateBorderSpace  
 Implementiert OLE-Client-Border-Aushandlung.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nBorderCmd`  
 Der Rahmen Aushandlung-Befehl. Finden Sie im Abschnitt "Hinweise" Mögliche Werte.  
  
 [in, out] `lpRectBorder`  
 Dimensionen des Rahmens.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Layout neu berechnet werden muss; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Werte für die `nBorderCmd` Parameter.  
  
 `borderGet`  
 Rufen Sie Speicherplatz für OLE-Client.  
  
 `borderRequest`  
 Erfordern Sie OLE-Client-Speicherplatz.  
  
 `borderSet`  
 Legen Sie die OLE-Client Speicherplatz.  
  
##  <a name="onactivate"></a>CFrameWndEx::OnActivate  
 Das Framework ruft diese Methode auf, wenn Benutzereingaben zu oder von den Frame gewechselt wird.  
  
```  
afx_msg void OnActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nState`  
 Gibt an, ob der Frame aktiv oder inaktiv ist. Siehe die Tabelle im Abschnitt "Hinweise", um mögliche Werte.  
  
 [in] `pWndOther`  
 Zeiger auf ein anderes Fenster, das Benutzereingaben mit dem aktuellen Element wechselt.  
  
 [in] `bMinimized`  
 Minimierten Zustand des Frames. `TRUE`Wenn der Frame minimiert wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Werte für die `nState` Parameter.  
  
 `WA_ACTIVE`  
 Der Rahmen wird von einer anderen Methode als ein Mausklick ausgewählt.  
  
 `WA_CLICKACTIVE`  
 Der Rahmen wird durch einen Mausklick ausgewählt.  
  
 `WA_INACTIVE`  
 Der Frame ist nicht ausgewählt.  
  
##  <a name="onactivateapp"></a>CFrameWndEx::OnActivateApp  
 Vom Framework aufgerufen, wenn die Anwendung aktiviert oder deaktiviert ist.  
  
```  
afx_msg void OnActivateApp(
    BOOL bActive,  
    DWORD dwThreadID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActive`  
 `TRUE`Wenn die Anwendung ausgewählt ist. `FALSE` , wenn die Anwendung nicht ausgewählt ist.  
  
 [in] `dwThreadID`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onchangevisualmanager"></a>CFrameWndEx::OnChangeVisualManager  
 Vom Framework aufgerufen, wenn eine Änderung des Frames, eine Änderung an der visuellen Manager erforderlich ist.  
  
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
  
##  <a name="onclose"></a>CFrameWndEx::OnClose  
 Das Framework ruft diese Methode, um den Frame zu schließen.  
  
```  
afx_msg void OnClose();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Frame im Seitenansichtsmodus ist, sendet er eine Windows-Meldung zu die Seitenansicht schließen; Wenn der Frame ein OLE-Clients hostet, wird, der Client deaktiviert.  
  
##  <a name="onclosedockingpane"></a>CFrameWndEx::OnCloseDockingPane  
 Vom Framework aufgerufen, wenn der Benutzer klickt auf die **schließen** auf einen andockbaren Bereich auf die Schaltfläche.  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane* pPane);
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der andockleiste geschlossen werden kann. `FALSE`andernfalls  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode, wenn Sie das Ausblenden der andockleiste behandeln möchten.  
  
##  <a name="oncloseminiframe"></a>CFrameWndEx::OnCloseMiniFrame  
 Vom Framework aufgerufen, wenn der Benutzer klickt auf die **schließen** Schaltfläche auf einem schwebenden Mini Rahmenfenster.  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein unverankertes Mini-Frame-Fenster geschlossen werden kann. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode, wenn Sie das Ausblenden eines unverankerten Mini-Frame-Fensters zu verarbeiten möchten.  
  
##  <a name="onclosepopupmenu"></a>CFrameWndEx::OnClosePopupMenu  
 Wird vom Framework aufgerufen, wenn ein aktives Popupmenü eine WM_DESTROY-Meldung verarbeitet.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Parameter  
 `pMenuPopup`  
 Ein Zeiger auf ein Popupmenü.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework sendet eine WM_DESTROY-Meldung an, wenn es gerade das Fenster zu schließen. Überschreiben Sie diese Methode, wenn Sie Benachrichtigungen von behandeln möchten `CMFCPopupMenu` Objekte, die zum Rahmenfenster gehören bei einem `CMFCPopupMenu` Objekt verarbeitet wird eine `WM_DESTROY` durch das Framework gesendet wird, wenn das Fenster geschlossen wird.  
  
##  <a name="oncmdmsg"></a>CFrameWndEx::OnCmdMsg  
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
 Befehlskategorie-Nachricht.  
  
 [in, out] `pExtra`  
 Ein Zeiger auf ein Command-Objekt.  
  
 [in, out] `pHandlerInfo`  
 Zeiger auf einen Befehl Handler-Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Befehlsnachricht übernommen wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oncontexthelp"></a>CFrameWndEx::OnContextHelp  
 Wird aufgerufen, durch das Framework zum Anzeigen von Hilfe Kontext beziehen.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oncreate"></a>CFrameWndEx::OnCreate  
 Vom Framework aufgerufen, nachdem der Rahmen erstellt wird.  
  
```  
afx_msg int OnCreate(LPCREATESTRUCT lpCreateStruct);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpCreateStruct`  
 Ein Zeiger auf die [CREATESTRUCT-Struktur](../../mfc/reference/createstruct-structure.md) für den neuen Rahmen.  
  
### <a name="return-value"></a>Rückgabewert  
 0, um die Frame-Erstellung fortsetzen; 1, um den Frame zu zerstören.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondestroy"></a>CFrameWndEx::OnDestroy  
 Vom Framework aufgerufen, wenn der Frame zerstört wird.  
  
```  
afx_msg void OnDestroy();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Zugriffstastentabelle, und alle Fenster zerstört werden.  
  
##  <a name="ondrawmenuimage"></a>CFrameWndEx::OnDrawMenuImage  
 Vom Framework aufgerufen, wenn die Anwendung das Bild, die einem Menüeelement zugeordneten Webseiteninhalte zeichnet.  
  
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
 Ein Zeiger auf eine Menüschaltfläche, dessen Bild gerendert wird.  
  
 [in] `rectImage`  
 Ein Zeiger auf eine `Rect` -Struktur, die die Bildschirmposition und die Größe des Bilds angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Framework erfolgreich das Bild rendert. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn die Image-Rendering für die Menüelemente anpassen, die auf der Menüleiste, die im Besitz von gehören sollen die `CFrameWndEx` abgeleitetes Objekt.  
  
##  <a name="ondrawmenulogo"></a>CFrameWndEx::OnDrawMenuLogo  
 Vom Framework aufgerufen, wenn ein `CMFCPopupMenu` Objekt verarbeitet eine WM_PAINT-Meldung.  
  
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
 Überschreiben Sie diese Funktion, wenn Sie ein Logo im Popupmenü anzuzeigen, die auf der Menüleiste, die im Besitz von gehört möchten die `CFrameWndEx` abgeleitetes Objekt.  
  
##  <a name="ondwmcompositionchanged"></a>CFrameWndEx::OnDWMCompositionChanged  
 Wird vom Framework aufgerufen, wenn es sich bei Desktop-Desktopfenster-Manager (DWM) Komposition aktiviert oder deaktiviert wurde.  
  
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
  
##  <a name="onexitsizemove"></a>CFrameWndEx::OnExitSizeMove  
 Vom Framework aufgerufen, wenn der Frame beendet wird, verschieben oder Ändern der Größe.  
  
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
  
##  <a name="ongetminmaxinfo"></a>CFrameWndEx::OnGetMinMaxInfo  
 Wird vom Framework aufgerufen, wenn es sich bei der Frame Fenster Dimension begrenzen angepasst wird.  
  
```  
afx_msg void OnGetMinMaxInfo(MINMAXINFO FAR* lpMMI);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpMMI`  
 Zeiger auf eine [MINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632605) Struktur.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onidleupdatecmdui"></a>CFrameWndEx::OnIdleUpdateCmdUI  
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
  
##  <a name="onlbuttondown"></a>CFrameWndEx::OnLButtonDown  
 Das Framework ruft diese Methode auf, wenn der Benutzer die linke Maustaste drückt.  
  
```  
afx_msg void OnLButtonDown(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFlags`  
 Gibt an, ob der Benutzer der Modifizierertasten. Mögliche Werte finden Sie in den Parameter `wParam` in [WM_LBUTTONDOWN Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms645607).  
  
 [in] `point`  
 Gibt an, die x- und y-Koordinaten des Zeigers, relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onlbuttonup"></a>CFrameWndEx::OnLButtonUp  
 Das Framework ruft diese Methode auf, wenn der Benutzer die linke Maustaste loslässt.  
  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFlags`  
 Gibt an, ob der Benutzer der Modifizierertasten. Mögliche Werte finden Sie in den Parameter `wParam` in [WM_LBUTTONUP Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms645608).  
  
 [in] `point`  
 Gibt an, die x- und y-Koordinaten des Zeigers, relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onmenubuttontoolhittest"></a>CFrameWndEx::OnMenuButtonToolHitTest  
 Vom Framework aufgerufen, wenn eine `CMFCToolBarButton` -Objekt Prozesse eine `WM_NCHITTEST` Nachricht.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf die Symbolleisten-Schaltfläche.  
  
 [out] `pTI`  
 Ein Zeiger auf ein Tool-Informationsstruktur.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Anwendung füllt die `pTI` Parameter. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie eine QuickInfo-Informationen zu einem bestimmten Menüelement bereitstellen möchten.  
  
##  <a name="onmenuchar"></a>CFrameWndEx::OnMenuChar  
 Vom Framework aufgerufen, wenn ein Menü angezeigt wird und der Benutzer drückt einen Schlüssel, der nicht an einen Befehl entsprechen.  
  
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
 Enthält die `MF_POPUP` Flag ist im angezeigten Menü ein Untermenü; enthält die `MF_SYSMENU` auszugeben, wenn Sie im angezeigten Menü eine Steuerelementmenü ist.  
  
 [in] `pMenu`  
 Ein Zeiger auf ein Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 Das höherwertige Wort muss es sich um einen der folgenden Werte sein.  
  
 `0`  
 Das Framework sollte die Tastatureingabe ignoriert werden.  
  
 `1`  
 Das Framework sollte das Menü zu schließen.  
  
 `2`  
 Das Framework sollten eines der Elemente angezeigt, die Sie im Menü auswählen. Das niederwertige Wort enthält die ID des Befehls auswählen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onmousemove"></a>CFrameWndEx::OnMouseMove  
 Das Framework ruft diese Methode auf, wenn der Mauszeiger bewegt wird.  
  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFlags`  
 Gibt an, ob ein Benutzer der Modifizierertasten. Mögliche Werte finden Sie in den Parameter `wParam` in [WM_MOUSEMOVE Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms645616).  
  
 [in] `point`  
 Gibt an, die x- und y Koordinaten des Mauszeigers relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onmoveminiframe"></a>CFrameWndEx::OnMoveMiniFrame  
 Vom Framework aufgerufen, wenn ein Fenster verschoben wird.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFrame`  
 Zeiger auf die [CPaneFrameWnd Klasse](../../mfc/reference/cpaneframewnd-class.md) Fensterbereichs.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Fenster nicht angedockt wurde; `FALSE` , wenn das Fenster angedockt ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onncactivate"></a>CFrameWndEx::OnNcActivate  
 Vom Framework aufgerufen, wenn der nicht-Clientbereich des Frames neu gezeichnet werden muss, um eine Änderung im aktiven Zustand anzuzeigen.  
  
```  
afx_msg BOOL OnNcActivate(BOOL bActive);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActive`  
 `TRUE`den aktive Frame gezeichnet werden soll; `FALSE` den inaktiven Rahmen gezeichnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null mit standardverarbeitung fortgesetzt; 0, um zu verhindern, dass nicht-Clientbereichs wird deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onnccalcsize"></a>CFrameWndEx::OnNcCalcSize  
 Vom Framework aufgerufen, wenn die Größe und Position des Clientbereichs berechnet werden müssen.  
  
```  
afx_msg void OnNcCalcSize(
    BOOL bCalcValidRects,  
    NCCALCSIZE_PARAMS FAR* lpncsp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCalcValidRects`  
 `TRUE`Wenn die Anwendung einen gültige Client-Bereich angeben müssen; andernfalls `FALSE`.  
  
 [in] `lpncsp`  
 Zeiger auf eine `NCCALCSIZE_PARAMS` -Struktur, die Frame-dimensionsänderungen enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onnchittest"></a>CFrameWndEx::OnNcHitTest  
 Wird vom Framework aufgerufen, wenn der Mauszeiger bewegt wird, oder wenn eine Maustaste gedrückt oder losgelassen wird.  
  
```  
afx_msg LRESULT OnNcHitTest(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die Position des Mauszeigers in Bildschirmkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger erreicht Enumerationswert. Eine Liste der möglichen Werte finden Sie unter [WM_NCHITTEST-Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms645618).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onncmousemove"></a>CFrameWndEx::OnNcMouseMove  
 Vom Framework aufgerufen, wenn der Mauszeiger in einem clientfremden Bereich.  
  
```  
afx_msg void OnNcMouseMove(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHitTest`  
 Ein Zeiger erreicht Enumerationswert. Eine Liste der möglichen Werte finden Sie unter [WM_NCHITTEST-Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms645618).  
  
 [in] `point`  
 Die Position des Mauszeigers in Bildschirmkoordinaten.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onncpaint"></a>CFrameWndEx::OnNcPaint  
 Vom Framework aufgerufen, wenn der nicht-Clientbereichs gezeichnet werden muss.  
  
```  
afx_msg void OnNcPaint();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onpanecheck"></a>CFrameWndEx::OnPaneCheck  
 Wird aufgerufen, durch das Framework, um die Sichtbarkeit eines Bereichs steuern.  
  
```  
afx_msg BOOL OnPaneCheck(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Steuerelement-ID eines Bereichs.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Befehl behandelt wurde. `FALSE` befehlsverarbeitung fortsetzen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onpostpreviewframe"></a>CFrameWndEx::OnPostPreviewFrame  
 Vom Framework aufgerufen, wenn der Benutzer die Seitenansicht ändert.  
  
```  
afx_msg LRESULT OnPostPreviewFrame(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wParam`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `lParam`  
 `TRUE`Wenn der Frame im Seitenansichtsmodus ist; `FALSE` Wenn Seitenansicht deaktiviert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onpowerbroadcast"></a>CFrameWndEx::OnPowerBroadcast  
 Vom Framework aufgerufen, wenn ein Power Management-Ereignis auftritt.  
  
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
 Führen Sie die standardmäßige Fensterprozedur aufrufen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onsetmenu"></a>CFrameWndEx::OnSetMenu  
 Wird aufgerufen, durch das Framework das Fenstermenü Frame zu ersetzen.  
  
```  
afx_msg LRESULT OnSetMenu(
    WPARAM wp,  
    LPARAM lp);  
  
BOOL OnSetMenu(HMENU hmenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wp`  
 Handle für das neue Menü der Frame-Fenster.  
  
 [in] `lp`  
 Handle für das neue Fenstermenü.  
  
 [in] `hmenu`  
 Handle für das neue Menü der Frame-Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 `LRESULT`ist das Ergebnis des Aufrufs von der Standardfensterprozedur.  
  
 `BOOL`ist `TRUE` war das Ereignis behandelt, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onsetpreviewmode"></a>CFrameWndEx::OnSetPreviewMode  
 Wird aufgerufen, durch das Framework für den Rahmen der Seitenansicht festgelegt.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bPreview`  
 `TRUE`So aktivieren Sie die Seitenansicht; `FALSE` Seitenansicht zu deaktivieren.  
  
 [in] `pState`  
 Zeiger auf eine `CPrintPreviewState` Zustandsstruktur frame.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onsettext"></a>CFrameWndEx::OnSetText  
 Vom Framework aufgerufen wird, legen Sie den Text eines Fensters.  
  
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
 Rückgabewert aus einem Aufruf von [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onshowcustomizepane"></a>CFrameWndEx::OnShowCustomizePane  
 Vom Framework aufgerufen, wenn er zeigt eine `QuickCustomizePane`.  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenuPane`  
 Ein Zeiger auf den schnellen anpassen, Bereich.  
  
 [in] `uiToolbarID`  
 Die Steuerelement-ID der Symbolleiste anpassen.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Anpassen der Quick Menü ist ein Popupmenü aufrufen, die angezeigt wird, wenn Sie auf der Symbolleiste anpassen Schaltfläche  
  
##  <a name="onshowpanes"></a>CFrameWndEx::OnShowPanes  
 Vom Framework aufgerufen, ein- oder Ausblenden von Bereichen.  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 `TRUE`Wenn die Anwendung wird, die Bereiche gezeigt: `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode immer `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung sind die Bereiche dargestellt. wenn `bShow` ist `TRUE` und die Bereiche ausgeblendet sind oder wenn `bShow` ist `FALSE` und die Bereiche sichtbar sind.  
  
 Die standardmäßige Implementierung Blendet die Bereiche aus, wenn `bShow` ist `TRUE` und die Bereiche werden angezeigt, oder wenn `bShow` ist `FALSE` und die Bereiche sind ausgeblendet.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum benutzerdefinierten Code ausführen, wenn das Framework Blendet oder Bereiche.  
  
##  <a name="onshowpopupmenu"></a>CFrameWndEx::OnShowPopupMenu  
 Vom Framework aufgerufen, wenn sie ein Popupmenü anzeigt.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenu`  
 Ein Zeiger auf ein Popupmenü.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Menü das Popupmenü sichtbar ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum benutzerdefinierten Code ausführen, wenn das Framework ein Popupmenü anzeigt. Angenommen, überschreiben Sie diese Methode, um die Hintergrundfarbe der Befehle in einem Popupmenü ändern.  
  
##  <a name="onsize"></a>CFrameWndEx::OnSize  
 Vom Framework aufgerufen, nach den Frame Fenstergröße ändert.  
  
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
  
##  <a name="onsizing"></a>CFrameWndEx::OnSizing  
 Vom Framework aufgerufen, wenn der Benutzer die Größe den Rahmen ändern.  
  
```  
afx_msg void OnSizing(
    UINT fwSide,  
    LPRECT pRect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `fwSide`  
 Der Rand des Frames, die verschoben werden. Der Parameter `wParam` in [WM_SIZING Benachrichtigung](http://msdn.microsoft.com/library/windows/desktop/ms632647).  
  
 [in, out] `pRect`  
 Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) oder [RECT](../../mfc/reference/rect-structure1.md) -Struktur, die die Frame-Koordinaten enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onsyscolorchange"></a>CFrameWndEx::OnSysColorChange  
 Wird vom Framework aufgerufen, wenn sich die Systemfarben ändern.  
  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ontearoffmenu"></a>CFrameWndEx::OnTearOffMenu  
 Vom Framework aufgerufen, wenn die Anwendung wird ein Menü angezeigt, die einen Balken abtrennbare verfügt.  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenuPopup`  
 Ein Zeiger auf ein Popupmenü.  
  
 [in] `pBar`  
 Ein Zeiger auf eine abtrennbarer Leiste.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Popup-Menü mit abtrennbarer Leiste aktiviert ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum benutzerdefinierten Code ausführen, wenn das Framework eine Steuerleiste angezeigt.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt, und gibt `TRUE`.  
  
##  <a name="ontoolbarcontextmenu"></a>CFrameWndEx::OnToolbarContextMenu  
 Wird aufgerufen, durch das Framework zum Erstellen einer Symbolleiste Popupmenü.  
  
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
  
##  <a name="ontoolbarcreatenew"></a>CFrameWndEx::OnToolbarCreateNew  
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
 Ein Zeiger auf den Text für die Titelleiste der Symbolleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die neue Symbolleiste; oder `NULL` , wenn eine Symbolleiste nicht erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ontoolbardelete"></a>CFrameWndEx::OnToolbarDelete  
 Vom Framework aufgerufen, wenn eine Symbolleiste gelöscht wird.  
  
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
  
##  <a name="onupdateframemenu"></a>CFrameWndEx::OnUpdateFrameMenu  
 Vom Framework aufgerufen wird, klicken Sie im Frame festgelegt.  
  
```  
virtual void OnUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMenuAlt`  
 Handle für den alternativen Menüs.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onupdateframetitle"></a>CFrameWndEx::OnUpdateFrameTitle  
 Das Framework ruft diese Methode, um die Titelleiste des Rahmenfensters zu aktualisieren.  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAddToTitle`  
 `TRUE`So fügen Sie den Titel des aktiven Dokuments auf die Titelleiste der Frame-Fensters; andernfalls`FALSE.`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onupdatepanemenu"></a>CFrameWndEx::OnUpdatePaneMenu  
 Vom Framework aufgerufen wird, klicken Sie im Bereich zu aktualisieren.  
  
```  
afx_msg void OnUpdatePaneMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pCmdUI`  
 Ein Zeiger auf das Benutzeroberflächenobjekt Bereich.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onwindowposchanged"></a>CFrameWndEx::OnWindowPosChanged  
 Vom Framework aufgerufen, wenn die Größe, Position oder Z-Reihenfolge wegen eines Aufrufs einer Verwaltungsmethode Fenster geändert wurde.  
  
```  
afx_msg void OnWindowPosChanged(WINDOWPOS FAR* lpwndpos);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpwndpos`  
 Zeiger auf eine [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) Struktur, die die neue Größe und Position enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="panefrompoint"></a>CFrameWndEx::PaneFromPoint  
 Sucht nach jeder Bereich für den angegebenen Punkt.  
  
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
 Erweitern Sie das Begrenzungsrechteck der jede Steuerleiste durch diese Menge an, bei der Suche nach Punkt.  
  
 [in] `bExactBar`  
 `TRUE`ignoriert die `nSensitivity` Parameter ist, andernfalls `FALSE`.  
  
 [in] `pRTCBarType`  
 Wenn dies nicht der `NULL`, sucht die Methode nur die Steuerleisten des angegebenen Typs.  
  
 [out] `dwAlignment`  
 Bei erfolgreicher Ausführung enthält dieser Parameter der Seite der Steuerleiste, die den angegebenen Punkt am nächsten liegt. Andernfalls ist dieser Parameter nicht initialisiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Steuerleiste, die enthält die `point`; `NULL` , wenn kein Steuerelement gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sucht die Steuerleisten in der Anwendung für eine `point`.  
  
 Verwendung `nSensitivity` Suchbereich zu vergrößern. Verwendung `pRTCBarType` um die Typen von Steuerleisten einzuschränken, die die Methode sucht.  
  
##  <a name="pretranslatemessage"></a>CFrameWndEx::PreTranslateMessage  
 Bestimmte Windows-Meldungen verarbeitet, bevor sie verteilt wurden.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMsg`  
 Ein Zeiger auf eine [MSG](../../mfc/reference/msg-structure1.md) Struktur, die die zu verarbeitende Meldung enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn die Nachricht verarbeitet und nicht weitergeleitet werden soll; 0, wenn die Nachricht nicht verarbeitet wurde und weitergeleitet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="recalclayout"></a>CFrameWndEx::RecalcLayout  
 Passt das Layout des Frames und zugehöriges untergeordnetes Fenster.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bNotify`  
 Gibt an, ob der OLE-Clientelement über die layoutänderung zu benachrichtigen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn die Größe des Rahmenfensters geändert hat oder Wenn Steuerleisten angezeigt oder ausgeblendet werden.  
  
##  <a name="removepanefromdockmanager"></a>CFrameWndEx::RemovePaneFromDockManager  
 Hebt die Registrierung auf einen Bereich, und entfernt sie aus der Dock-Manager.  
  
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
 Ein Zeiger auf das Steuerelement-Leistenbereich zu entfernen.  
  
 [in] `bDestroy`  
 `TRUE`Steuerleiste zerstört nach dem Entfernen; `FALSE` andernfalls.  
  
 [in] `bAdjustLayout`  
 `TRUE`Layout des Docks anpassen; `FALSE` andernfalls.  
  
 [in] `bAutoHide`  
 `TRUE`Wenn die Steuerleiste im automatischen Ausblendemodus ist; `FALSE` andernfalls.  
  
 [in] `pBarReplacement`  
 Ein Zeiger auf einen Bereich, der Bereich entfernten ersetzt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Steuerleiste am Layout Docks des Rahmenfensters aufheben.  
  
 Die [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) behandelt das Layout von Steuerleisten. Sie müssen jede Steuerleiste beim Dock-Manager registrieren, indem Sie mit der [CFrameWndEx::AddPane](#addpane) Methode oder die [CFrameWndEx::InsertPane](#insertpane) Methode.  
  
##  <a name="setdockstate"></a>CFrameWndEx::SetDockState  
 Stellt den andockzustand in der Registrierung gespeicherten am Layout des Docks wieder her.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Parameter  
 `state`  
 Den andockzustand. Dieser Parameter wird ignoriert.  
  
##  <a name="setprintpreviewframe"></a>CFrameWndEx::SetPrintPreviewFrame  
 Legt das Rahmenfenster Seitenansicht zu blättern.  
  
```  
void SetPrintPreviewFrame(CFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf eine Seitenansicht Rahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setuptoolbarmenu"></a>CFrameWndEx::SetupToolbarMenu  
 Fügt eine benutzerdefinierte Befehle in einem Symbolleistenmenüs.  
  
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
 Die erste benutzerdefinierte-Befehl.  
  
 [in] `uiViewUserToolbarCmdLast`  
 Der letzte benutzerdefinierte-Befehl.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework benutzerdefinierte Befehle in einer Liste gespeichert. Verwendung `uiViewUserToolbarCmdFirst` und `uiViewUserToolbarCmdList` die Indizes der Befehle zum Einfügen an.  
  
##  <a name="showfullscreen"></a>CFrameWndEx::ShowFullScreen  
 Schaltet den Hauptframe zwischen dem Vollbildmodus und dem normalen Modus.  
  
```  
void ShowFullScreen();
```  
  
##  <a name="showpane"></a>CFrameWndEx::ShowPane  
 Zeigt an oder blendet Sie aus dem angegebenen Bereich.  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf die Steuerleiste angezeigt oder ausgeblendet werden soll.  
  
 [in] `bShow`  
 Wenn `TRUE`, die Anwendung zeigt die Steuerleiste. Andernfalls wird die Anwendung die Steuerleiste ausgeblendet.  
  
 [in] `bDelay`  
 Wenn `TRUE`, die Anpassung von Layout des Docks zu verzögern, bis das Framework ruft [CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout). Andernfalls, neu berechnen Sie sofort am Layout des Docks.  
  
 [in] `bActivate`  
 Wenn `TRUE`, aktivieren Sie die Steuerleiste. Andernfalls werden die Steuerleiste in einen inaktiven Status angezeigt.  
  
##  <a name="updatecaption"></a>CFrameWndEx::UpdateCaption  
 Wird aufgerufen, durch das Framework die framebeschriftung Fenster zu aktualisieren.  
  
```  
void UpdateCaption();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="winhelp"></a>CFrameWndEx::WinHelp  
 Ruft die WinHelp-Anwendung oder das Kontextmenü im Zusammenhang Hilfe.  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Parameter  
 `dwData`  
 Daten, die von abhängig ist die `nCmd` Parameter. Eine Liste der möglichen Werte finden Sie unter [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267).  
  
 `nCmd`  
 Der Help-Befehl. Eine Liste der möglichen Werte finden Sie unter [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267).  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)
