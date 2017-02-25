---
title: "CBasePane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBasePane::get_accKeyboardShortcut"
  - "CBasePane.get_accKeyboardShortcut"
  - "CBasePane.accSelect"
  - "get_accDefaultAction"
  - "accSelect"
  - "CBasePane.accHitTest"
  - "CBasePane.get_accRole"
  - "get_accKeyboardShortcut"
  - "CBasePane::Serialize"
  - "CBasePane"
  - "CBasePane::get_accDefaultAction"
  - "get_accParent"
  - "CBasePane::accSelect"
  - "accLocation"
  - "CBasePane.get_accDescription"
  - "get_accName"
  - "CBasePane::get_accChildCount"
  - "CBasePane.get_accChild"
  - "CBasePane::accHitTest"
  - "accHitTest"
  - "get_accHelp"
  - "CBasePane.get_accChildCount"
  - "CBasePane.get_accValue"
  - "CBasePane::get_accDescription"
  - "get_accChildCount"
  - "CBasePane.accLocation"
  - "CBasePane.PreTranslateMessage"
  - "CBasePane.get_accName"
  - "PreTranslateMessage"
  - "CBasePane::get_accFocus"
  - "get_accDescription"
  - "CBasePane::get_accRole"
  - "get_accValue"
  - "CBasePane.Serialize"
  - "CBasePane::accLocation"
  - "get_accRole"
  - "CBasePane::get_accChild"
  - "get_accFocus"
  - "CBasePane::get_accHelp"
  - "CBasePane.get_accDefaultAction"
  - "CBasePane.get_accHelp"
  - "CBasePane::PreTranslateMessage"
  - "CBasePane::get_accState"
  - "CBasePane.get_accParent"
  - "CBasePane::get_accParent"
  - "get_accChild"
  - "CBasePane::get_accValue"
  - "Serialize"
  - "get_accState"
  - "CBasePane.get_accState"
  - "CBasePane.get_accFocus"
  - "CBasePane::get_accName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accHitTest method"
  - "accLocation method"
  - "accSelect method"
  - "CBasePane class"
  - "get_accChild method"
  - "get_accChildCount method"
  - "get_accDefaultAction method"
  - "get_accDescription method"
  - "get_accFocus method"
  - "get_accHelp method"
  - "get_accKeyboardShortcut method"
  - "get_accName method"
  - "get_accParent method"
  - "get_accRole method"
  - "get_accState method"
  - "get_accValue method"
  - "PreTranslateMessage method"
  - "Serialize method"
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
caps.latest.revision: 43
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 44
---
# CBasePane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Basisklasse für alle Bereiche in MFC.  
  
## Syntax  
  
```  
class CBasePane : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CBasePane::CBasePane`|Standardkonstruktor.|  
|`CBasePane::~CBasePane`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|`CBasePane::accHitTest`|Aufgerufen vom Framework, um das untergeordnete Element oder das untergeordnete Objekt an einem angegebenen Punkt auf dem Bildschirm abzurufen.  \(Überschreibungen [CWnd::accHitTest](../Topic/CWnd::accHitTest.md).\)|  
|`CBasePane::accLocation`|Aufgerufen vom Framework, um die aktuelle Bildschirmposition für das angegebene Objekt abzurufen.  \(Überschreibungen [CWnd::accLocation](../Topic/CWnd::accLocation.md).\)|  
|[CBasePane::AccNotifyObjectFocusEvent](../Topic/CBasePane::AccNotifyObjectFocusEvent.md)|`CBasePane` verwendet diese Methode nicht.|  
|`CBasePane::accSelect`|Aufgerufen durch das Framework, um die Auswahl zu ändern oder den Tastaturfokus des angegebenen Objekts zu verschieben.  \(Überschreibungen [CWnd::accSelect](../Topic/CWnd::accSelect.md).\)|  
|[CBasePane::AddPane](../Topic/CBasePane::AddPane.md)|Fügt einen Bereich dem Andocken Manager hinzu.|  
|[CBasePane::AdjustDockingLayout](../Topic/CBasePane::AdjustDockingLayout.md)|Leitet einen Aufruf zum Andocken Manager um, um das andockbare Layout anzupassen.|  
|[CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md)|Aufgerufen vom Framework, wenn der Bereich seine interne Layout anpassen soll.|  
|[CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md)|Berechnet die horizontale Größe einer Steuerleiste.|  
|[CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md)|Bestimmt, ob ein anderer Bereich in den Bereich angedockt werden kann.|  
|[CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md)|Bestimmt, ob der Bereich Modus "Automatisches Ausblenden" unterstützt.|  
|[CBasePane::CanBeAttached](../Topic/CBasePane::CanBeAttached.md)|Bestimmt, ob der Bereich zu einem anderen Bereich angedockt werden kann.|  
|[CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)|Bestimmt, ob der Bereich geschlossen werden kann.|  
|[CBasePane::CanBeDocked](../Topic/CBasePane::CanBeDocked.md)|Bestimmt, ob der Bereich zu einem anderen Bereich angedockt werden kann.|  
|[CBasePane::CanBeResized](../Topic/CBasePane::CanBeResized.md)|Bestimmt, ob der Bereich angepasst werden kann.|  
|[CBasePane::CanBeTabbedDocument](../Topic/CBasePane::CanBeTabbedDocument.md)|Gibt an, ob der Bereich zu einem MDI mit den versehenen Dokument konvertiert werden kann.|  
|[CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md)|Bestimmt, ob der Bereich Float kann.|  
|[CBasePane::CanFocus](../Topic/CBasePane::CanFocus.md)|Gibt an, ob der Bereich den Fokus erhalten kann.|  
|[CBasePane::CopyState](../Topic/CBasePane::CopyState.md)|Kopiert den Zustand eines angegebenen Bereichs.|  
|[CBasePane::CreateDefaultMiniframe](../Topic/CBasePane::CreateDefaultMiniframe.md)|Wenn der Bereich Float kann, bietet ein Minirahmenfenster erstellt.|  
|[CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md)|Erstellt das Pane\-Steuerelement.|  
|[CBasePane::DockPane](../Topic/CBasePane::DockPane.md)|Dockt einen Bereich zu einem anderen Bereich oder einem Rahmenfenster an.|  
|[CBasePane::DockPaneUsingRTTI](../Topic/CBasePane::DockPaneUsingRTTI.md)|Dockt den Bereich mithilfe von Laufzeit\-Typeninformation an.|  
|[CBasePane::DockToFrameWindow](../Topic/CBasePane::DockToFrameWindow.md)|Dockt ein andockbares Fenster zu Frame anzuzeigen.|  
|[CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md)|Bestimmt, ob ein anderer Bereich zwischen diesen Bereich und die übergeordneten Frames dynamisch eingefügt werden kann.|  
|[CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md)|Aktiviert Andocken des Bereichs zum Großrechner.|  
|[CBasePane::EnableGripper](../Topic/CBasePane::EnableGripper.md)|Aktiviert oder deaktiviert den Ziehpunkt.  Wenn der Ziehpunkt aktiviert ist, kann der Benutzer ziehen, um den Bereich neu anzuordnen.|  
|`CBasePane::FillWindowRect`|Wird intern verwendet.|  
|[CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md)|Schwimmt den Bereich.|  
|`CBasePane::get_accChild`|Aufgerufen durch das Framework, um die Adresse einer `IDispatch`\-Schnittstelle für das angegebene untergeordnete Element abzurufen.  \(Überschreibungen [CWnd::get\_accChild](../Topic/CWnd::get_accChild.md).\)|  
|`CBasePane::get_accChildCount`|Aufgerufen vom Framework, um die Anzahl untergeordneter Elemente ab, die diesem Objekt gehören.  \(Überschreibungen [CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md).\)|  
|`CBasePane::get_accDefaultAction`|Aufgerufen durch das Framework, um eine Zeichenfolge abzurufen, die die Standardaktion für das Objekt beschrieben wird.  \(Überschreibungen [CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md).\)|  
|`CBasePane::get_accDescription`|Aufgerufen durch Framework, um eine Zeichenfolge abzurufen, die die visuelle Darstellung des angegebenen Objekts beschreibt.  \(Überschreibungen [CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md).\)|  
|`CBasePane::get_accFocus`|Aufgerufen durch das Framework, um das Objekt ab, das den Tastaturfokus hat.  \(Überschreibungen [CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md).\)|  
|`CBasePane::get_accHelp`|Aufgerufen vom Framework, um eine Hilfeeigenschaftzeichenfolge für das Objekt abzurufen.  \(Überschreibungen [CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md).\)|  
|[CBasePane::get\_accHelpTopic](../Topic/CBasePane::get_accHelpTopic.md)|Aufgerufen vom Framework, um den vollständigen Pfad des WinHelpfile  abzurufen, das dem angegebenen Objekt und dem entsprechenden Bezeichner des Themas in dieser Datei zugeordnet ist.  \(Überschreibungen [CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md).\)|  
|`CBasePane::get_accKeyboardShortcut`|Aufgerufen durch das Framework, um die angegebene Tastenkombination für das Objekt abzurufen.  \(Überschreibungen [CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md).\)|  
|`CBasePane::get_accName`|Aufgerufen vom Framework, um den Namen des angegebenen Objekts abzurufen.  \(Überschreibungen [CWnd::get\_accName](../Topic/CWnd::get_accName.md).\)|  
|`CBasePane::get_accParent`|Aufgerufen vom Framework, um die `IDispatch`\-Schnittstelle für das übergeordnete Element des Objekts abzurufen.  \(Überschreibungen [CWnd::get\_accParent](../Topic/CWnd::get_accParent.md).\)|  
|`CBasePane::get_accRole`|Aufgerufen vom Framework, um Informationen abzurufen, die die Rolle des angegebenen Objekts beschreibt.  \(Überschreibungen [CWnd::get\_accRole](../Topic/CWnd::get_accRole.md).\)|  
|[CBasePane::get\_accSelection](../Topic/CBasePane::get_accSelection.md)|Aufgerufen vom Framework, um die ausgewählten untergeordneten Elemente aus diesem abzurufenden Objekts.  \(Überschreibungen [CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md).\)|  
|`CBasePane::get_accState`|Aufgerufen vom Framework, um den aktuellen Zustand des angegebenen Objekts abzurufen.  \(Überschreibungen [CWnd::get\_accState](../Topic/CWnd::get_accState.md).\)|  
|`CBasePane::get_accValue`|Aufgerufen vom Framework, um den Wert des angegebenen Objekts abzurufen.  \(Überschreibungen [CWnd::get\_accValue](../Topic/CWnd::get_accValue.md).\)|  
|[CBasePane::GetCaptionHeight](../Topic/CBasePane::GetCaptionHeight.md)|Gibt die Beschriftungshöhe zurück.|  
|[CBasePane::GetControlBarStyle](../Topic/CBasePane::GetControlBarStyle.md)|Gibt das Steuerleistenformat zurück.|  
|[CBasePane::GetCurrentAlignment](../Topic/CBasePane::GetCurrentAlignment.md)|Gibt die aktuelle Bereichsausrichtung zurück.|  
|[CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md)|Gibt den aktuellen Andockmodus für den Bereich zurück.|  
|[CBasePane::GetDockSiteFrameWnd](../Topic/CBasePane::GetDockSiteFrameWnd.md)|Gibt einen Zeiger auf das Fenster zurück, das die Docksite für den Bereich ist.|  
|[CBasePane::GetEnabledAlignment](../Topic/CBasePane::GetEnabledAlignment.md)|Gibt die CBRS\_ALIGN\_\-Formate zurück, die dem Bereich angewendet werden.|  
|[CBasePane::GetMFCStyle](../Topic/CBasePane::GetMFCStyle.md)|Gibt die Bereichsformate zurück, die MFC spezifisch sind.|  
|[CBasePane::GetPaneIcon](../Topic/CBasePane::GetPaneIcon.md)|Gibt ein Handle für Bereichssymbol zurück.|  
|`CBasePane::GetPaneRect`|Wird intern verwendet.|  
|[CBasePane::GetPaneRow](../Topic/CBasePane::GetPaneRow.md)|Gibt einen Zeiger auf [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)\-Objekt zurück, in dem der Bereich angedockt ist.|  
|[CBasePane::GetPaneStyle](../Topic/CBasePane::GetPaneStyle.md)|Gibt das Bereichsformat zurück.|  
|[CBasePane::GetParentDockSite](../Topic/CBasePane::GetParentDockSite.md)|Gibt einen Zeiger auf die Elemente Docksite zurück.|  
|[CBasePane::GetParentMiniFrame](../Topic/CBasePane::GetParentMiniFrame.md)|Gibt einen Zeiger auf Elementen Minirahmenfenster zurück.|  
|[CBasePane::GetParentTabbedPane](../Topic/CBasePane::GetParentTabbedPane.md)|Gibt einen Zeiger auf die Elemente Seite im Registerformat zurück.|  
|[CBasePane::GetParentTabWnd](../Topic/CBasePane::GetParentTabWnd.md)|Gibt einen Zeiger auf das übergeordnete Fenster zurück, das in einer Registerkarte ist.|  
|[CBasePane::GetRecentVisibleState](../Topic/CBasePane::GetRecentVisibleState.md)|Das Framework ruft diese Methode auf, wenn ein Bereich von einem Archiv wiederhergestellt wird.|  
|[CBasePane::HideInPrintPreviewMode](../Topic/CBasePane::HideInPrintPreviewMode.md)|Gibt an, ob der Bereich in der Seitenansicht ausgeblendet ist.|  
|[CBasePane::InsertPane](../Topic/CBasePane::InsertPane.md)|Registriert den angegebenen Bereich mit dem Andocken Manager.|  
|[CBasePane::IsAccessibilityCompatible](../Topic/CBasePane::IsAccessibilityCompatible.md)|Gibt an, ob der Bereich Active Accessibility unterstützt.|  
|[CBasePane::IsAutoHideMode](../Topic/CBasePane::IsAutoHideMode.md)|Bestimmt, ob ein Bereich im Modus "Automatisches Ausblenden" ist.|  
|[CBasePane::IsDialogControl](../Topic/CBasePane::IsDialogControl.md)|Gibt an, ob der Bereich ein Dialogfeld\-Steuerelement ist.|  
|[CBasePane::IsDocked](../Topic/CBasePane::IsDocked.md)|Bestimmt, ob der Bereich angedockt ist.|  
|[CBasePane::IsFloating](../Topic/CBasePane::IsFloating.md)|Bestimmt, ob der Bereich unverankert ist.|  
|[CBasePane::IsHorizontal](../Topic/CBasePane::IsHorizontal.md)|Bestimmt, ob der Bereich horizontal angedockt wird.|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](../Topic/CBasePane::IsInFloatingMultiPaneFrameWnd.md)|Gibt an, ob der Bereich in einem Rahmenfenster mit mehreren Bereichen ist.|  
|[CBasePane::IsMDITabbed](../Topic/CBasePane::IsMDITabbed.md)|Bestimmt, ob der Bereich zu einem untergeordneten MDI\-Fenster als Dokument im Registerkartenformat hinzugefügt wurde.|  
|[CBasePane::IsPaneVisible](../Topic/CBasePane::IsPaneVisible.md)|Gibt an, ob das `WS_VISIBLE`\-Flag für den Bereich festgelegt wird.|  
|[CBasePane::IsPointNearDockSite](../Topic/CBasePane::IsPointNearDockSite.md)|Bestimmt, ob ein bestimmter Punkt neben der Docksite ist.|  
|[CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md)|Bestimmt, ob der Bereich angepasst werden kann.|  
|[CBasePane::IsRestoredFromRegistry](../Topic/CBasePane::IsRestoredFromRegistry.md)|Bestimmt, ob der Bereich aus der Registrierung wiederhergestellt wird.|  
|[CBasePane::IsTabbed](../Topic/CBasePane::IsTabbed.md)|Bestimmt, ob der Bereich in das Tab\-Steuerelement eines Fensters im Registerkartenformat eingefügt wurde.|  
|`CBasePane::IsTooltipTopmost`|Wird intern verwendet.|  
|[CBasePane::IsVisible](../Topic/CBasePane::IsVisible.md)|Bestimmt, ob der Bereich sichtbar ist.|  
|[CBasePane::LoadState](../Topic/CBasePane::LoadState.md)|Lädt den Bereichszustand aus der Registrierung.|  
|[CBasePane::MoveWindow](../Topic/CBasePane::MoveWindow.md)|Verschiebt den Bereich.|  
|[CBasePane::OnAfterChangeParent](../Topic/CBasePane::OnAfterChangeParent.md)|Aufgerufen vom Framework, wenn das übergeordnete Element des Bereichs geändert wurde.|  
|[CBasePane::OnBeforeChangeParent](../Topic/CBasePane::OnBeforeChangeParent.md)|Aufgerufen vom Framework vor dem Bereich ändert das übergeordnete Fenster.|  
|[CBasePane::OnDrawCaption](../Topic/CBasePane::OnDrawCaption.md)|Das Framework ruft diese Methode auf, wenn die Beschriftung gezeichnet wird.|  
|[CBasePane::OnMovePaneDivider](../Topic/CBasePane::OnMovePaneDivider.md)|Diese Methode wird momentan nicht verwendet.|  
|[CBasePane::OnPaneContextMenu](../Topic/CBasePane::OnPaneContextMenu.md)|Aufgerufen vom Framework, wenn ein Menü erstellt, das eine Liste von Bereichen umfasst.|  
|[CBasePane::OnRemoveFromMiniFrame](../Topic/CBasePane::OnRemoveFromMiniFrame.md)|Aufgerufen vom Framework ausgelöst, wenn ein Bereich von übergeordneten Minirahmenfenster entfernt wird.|  
|[CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md)|`CBasePane` verwendet diese Methode nicht.|  
|`CBasePane::OnUpdateCmdUI`|Wird intern verwendet.|  
|[CBasePane::PaneFromPoint](../Topic/CBasePane::PaneFromPoint.md)|Gibt den Bereich zurück, der den angegebenen Punkt enthält.|  
|`CBasePane::PreTranslateMessage`|Wird von Klasse [CWinApp](../../mfc/reference/cwinapp-class.md), um Fenstermeldungen zu übersetzen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  \(Überschreibungen [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CBasePane::RecalcLayout](../Topic/CBasePane::RecalcLayout.md)|`CBasePane` verwendet diese Methode nicht.|  
|[CBasePane::RemovePaneFromDockManager](../Topic/CBasePane::RemovePaneFromDockManager.md)|Hebt einen Bereich Registrierung auf und entfernt sie aus der Liste im Andocken Manager.|  
|[CBasePane::SaveState](../Topic/CBasePane::SaveState.md)|Rettet den Zustand des Bereichs in die Registrierung.|  
|[CBasePane::SelectDefaultFont](../Topic/CBasePane::SelectDefaultFont.md)|Wählt die Standardschriftart für einen angegebenen Gerätekontext aus.|  
|`CBasePane::Serialize`|Liest oder Schreiben dieses Objekt von oder einem Archiv.  \(Überschreibungen [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CBasePane::SetControlBarStyle](../Topic/CBasePane::SetControlBarStyle.md)|Legt das Steuerleistenformat fest.|  
|[CBasePane::SetDockingMode](../Topic/CBasePane::SetDockingMode.md)|Legt den Andockmodus für den Bereich fest.|  
|`CBasePane::SetMDITabbed`|Wird intern verwendet.|  
|[CBasePane::SetPaneAlignment](../Topic/CBasePane::SetPaneAlignment.md)|Legt die Ausrichtung für den Bereich fest.|  
|`CBasePane::SetPaneRect`|Wird intern verwendet.|  
|[CBasePane::SetPaneStyle](../Topic/CBasePane::SetPaneStyle.md)|Legt das Format des Bereichs fest.|  
|`CBasePane::SetRestoredFromRegistry`|Wird intern verwendet.|  
|[CBasePane::SetWindowPos](../Topic/CBasePane::SetWindowPos.md)|Ändert die Größe, Position und die Z\-Reihenfolge eines Bereichs.|  
|[CBasePane::ShowPane](../Topic/CBasePane::ShowPane.md)|In oder aus der Bereich.|  
|[CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md)|Streckt einen Bereich vertikal oder horizontal.|  
|[CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md)|Entfernt den Bereich von der Docksite, vom Standardwert Schieberegler oder vom Minirahmenfenster, in dem er gerade angedockt ist.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CBasePane::DoPaint](../Topic/CBasePane::DoPaint.md)|Füllt den Hintergrund des Bereichs aus.|  
  
## Hinweise  
 Wenn Sie eine Bereichsklasse erstellen möchten, die die erweiterten Andocken Funktionen unterstützt, die in MFC verfügbar sind, müssen Sie es aus `CBasePane` oder von [CPane Class](../../mfc/reference/cpane-class.md) berechnen.  
  
## Anpassungs\-Tipps  
 Die folgenden Anpassungstipps betreffen [CBasePane Class](../../mfc/reference/cbasepane-class.md) und alle Klassen, die davon erben:  
  
-   Wenn Sie einen Bereich erstellen, können Sie mehrere neue Formate anwenden:  
  
    -   `AFX_CBRS_FLOAT` stellt den Bereich wird nun erstellt.  
  
    -   `AFX_CBRS_AUTOHIDE` aktiviert Modus "Automatisches Ausblenden".  
  
    -   `AFX_CBRS_CLOSE` aktiviert den geschlossen werden, \(Bereich ausgeblendet wurde\).  
  
     Diese sind Flags, die Sie mit einer bitweisen OR\-Operation kombiniert werden können.  
  
     `CBasePane` implementiert die folgenden booleschen virtuellen Methoden, um diese Flags wiederzugeben: [CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md), [CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md), [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md).  Sie können sie in abgeleiteten Klassen überschreiben, um deren Verhalten anzupassen.  
  
-   Sie können Dockverhalten anpassen, indem Sie [CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md) überschreiben.  Haben Sie die Bereichsrückgabe `FALSE` dieser Methode, um einen anderen Bereichs am Andocken zu verhindern.  
  
-   Wenn Sie einen statischen Bereich erstellen möchten, der nicht Fenstern können und der einen anderen Bereich am Andocken davor verhindert \(ähnlich der Outlook\-Leiste im OutlookDemo\-Beispiel\), erstellen Sie es als nicht\-unverankertes und überschreiben Sie [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md), um `FALSE` zurückzugeben.  Die Standardimplementierung gibt `FALSE` zurück, wenn der Bereich ohne das `AFX_CBRS_FLOAT` Format erstellt wird.  
  
-   Stellen Sie alle Bereiche mit IDs auf \-1 erstellt.  
  
-   Um Bereichssichtbarkeit zu bestimmen, verwenden Sie [CBasePane::IsVisible](../Topic/CBasePane::IsVisible.md).  Sie verarbeitet ordnungsgemäß den Sichtbarkeitszustand in im Registerkartenformat und in den Modi "Automatisches Ausblenden".  
  
-   Wenn Sie einen nicht\-unverankerten in der Größe veränderbaren Bereich erstellen möchten, erstellen Sie ihn ohne das `AFX_CBRS_FLOAT` Format erstellt und rufen Sie [CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md) auf.  
  
-   Um einen Bereich von einem Andocken Layout auszuschließen oder eine Symbolleiste aus der Dockleiste zu entfernen, rufen Sie [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md) auf.  Rufen Sie diese Methode nicht für Bereiche im Modus "Automatisches Ausblenden" oder für Bereiche aufgeführt, die in den Registerkarten von Fenstern im Registerkartenformat befinden.  
  
-   Wenn Sie einen Bereich Float oder abdocken möchten, der im Modus "Automatisches Ausblenden" ist, müssen Sie [CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md) mit `FALSE` aufrufen während das erste Argument, bevor Sie [CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md) oder [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md) aufrufen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CBasePane` verwendet.  Das Beispiel zeigt, wie ein Bereich von der `CFrameWndEx`\-Klasse abgerufen und wie den Andockmodus, die Bereichsausrichtung und das Bereichsformat festgelegt wird.  Der Code ist von [Word\-Auflagenbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_WordPad#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_WordPad#2)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
## Anforderungen  
 **Header:** afxbasepane.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)