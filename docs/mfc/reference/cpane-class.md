---
title: "CPane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPane class"
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse `CPane` ist eine Erweiterung [CControlBar Class](../../mfc/reference/ccontrolbar-class.md).  Wenn Sie ein vorhandenes MFC\-Projekt aktualisieren, ersetzen Sie alle Vorkommen von `CControlBar` durch `CPane`.  
  
## Syntax  
  
```  
class CPane : public CBasePane  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CPane::~CPane`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPane::AdjustSizeImmediate](../Topic/CPane::AdjustSizeImmediate.md)|Berechnet sofort das Layout eines Bereichs neu.|  
|[CPane::AllocElements](../Topic/CPane::AllocElements.md)|Ordnet Speicher für die interne Verwendung zu.|  
|[CPane::AllowShowOnPaneMenu](../Topic/CPane::AllowShowOnPaneMenu.md)|Gibt an, ob der Bereich in der von der Runtime generierten Liste von Bereichen für die Anwendung aufgeführt ist.|  
|[CPane::CalcAvailableSize](../Topic/CPane::CalcAvailableSize.md)|Berechnet den Unterschied an Größe zwischen einem angegebenen Rechteck und dem Rechteck des aktiven Fensters.|  
|[CPane::CalcInsideRect](../Topic/CPane::CalcInsideRect.md)|Berechnet das innere Rechteck eines Bereichs und berücksichtigt die Ränder und der Ziehpunkte.|  
|[CPane::CalcRecentDockedRect](../Topic/CPane::CalcRecentDockedRect.md)|Berechnet das vor kurzem angedockte Rechteck.|  
|[CPane::CalcSize](../Topic/CPane::CalcSize.md)|Berechnet die Größe des Bereichs.|  
|[CPane::CanBeDocked](../Topic/CPane::CanBeDocked.md)|Bestimmt, ob der Bereich am angegebenen niedrigen Bereich angedockt werden kann.|  
|[CPane::CanBeTabbedDocument](../Topic/CPane::CanBeTabbedDocument.md)|Bestimmt, ob der Bereich zu einem Dokument im Registerkartenformat konvertiert werden kann.|  
|[CPane::ConvertToTabbedDocument](../Topic/CPane::ConvertToTabbedDocument.md)|Konvertiert ein andockbares Fenster zu einem Dokument im Registerkartenformat.|  
|[CPane::CopyState](../Topic/CPane::CopyState.md)|Kopiert den Zustand eines Bereichs.  \(Überschreibungen [CBasePane::CopyState](../Topic/CBasePane::CopyState.md).\)|  
|[CPane::Create](../Topic/CPane::Create.md)|Erstellt eine Steuerleiste und fügt sie dem `CPane`\-Objekt.|  
|[CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md)|Stellt ein Minirahmenfenster für einen unverankerten Bereich erstellt.|  
|[CPane::CreateEx](../Topic/CPane::CreateEx.md)|Erstellt eine Steuerleiste und fügt sie dem `CPane`\-Objekt.|  
|`CPane::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CPane::DockByMouse](../Topic/CPane::DockByMouse.md)|Dockt einen Bereich mithilfe der Methode Andocken der Maus an.|  
|[CPane::DockPane](../Topic/CPane::DockPane.md)|Dockt beweglichen den Bereich auf einen niedrigen Bereich an.|  
|[CPane::DockPaneStandard](../Topic/CPane::DockPaneStandard.md)|Dockt einen Bereich mithilfe des durch Andocken der Kontur \(Standard\) an.|  
|[CPane::DockToFrameWindow](../Topic/CPane::DockToFrameWindow.md)|Dockt ein andockbares Fenster zu Frame anzuzeigen.  \(Überschreibungen `CBasePane::DockToFrameWindow`.\)|  
|[CPane::DoesAllowSiblingBars](../Topic/CPane::DoesAllowSiblingBars.md)|Gibt an, ob Sie einen anderen Bereich an derselben Zeile andocken können, in der der aktuelle Bereich angedockt ist.|  
|[CPane::FloatPane](../Topic/CPane::FloatPane.md)|Schwimmt den Bereich.|  
|[CPane::GetAvailableExpandSize](../Topic/CPane::GetAvailableExpandSize.md)|Gibt die Menge, in Pixel zurück, die der Bereich erweitern können.|  
|[CPane::GetAvailableStretchSize](../Topic/CPane::GetAvailableStretchSize.md)|Gibt die Menge, in Pixel zurück, die der Bereich verkleinern kann.|  
|[CPane::GetBorders](../Topic/CPane::GetBorders.md)|Gibt die Breite des Rahmens des Bereichs zurück.|  
|[CPane::GetClientHotSpot](../Topic/CPane::GetClientHotSpot.md)|Gibt den *Hotspot* für den Bereich zurück.|  
|[CPane::GetDockSiteRow](../Topic/CPane::GetDockSiteRow.md)|Gibt die Dockzeile zurück, in der der Bereich angedockt ist.|  
|[CPane::GetExclusiveRowMode](../Topic/CPane::GetExclusiveRowMode.md)|Bestimmt, ob der Bereich im exklusiven Zeilenmodus ist.|  
|[CPane::GetHotSpot](../Topic/CPane::GetHotSpot.md)|Gibt den Hotspot zurück, der in einem zugrunde liegenden `CMFCDragFrameImpl`\-Objekt gespeichert wird.|  
|[CPane::GetMinSize](../Topic/CPane::GetMinSize.md)|Ruft das Minimum ab, dessen Größe für den Bereich zulässig ist.|  
|[CPane::GetPaneName](../Topic/CPane::GetPaneName.md)|Ruft den Namen für den Bereich.|  
|`CPane::GetResizeStep`|Wird intern verwendet.|  
|`CPane::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CPane::GetVirtualRect](../Topic/CPane::GetVirtualRect.md)|Ruft das *virtuelle Rechteck des* Bereichs ab.|  
|[CPane::IsChangeState](../Topic/CPane::IsChangeState.md)|Während der Bereich verschoben wird, analysiert diese Methode die Position des Bereichs relativ zu anderen Bereichen, dockt Zeilen und Minirahmenfenster und gibt der entsprechende `AFX_CS_STATUS`\-Wert an.|  
|[CPane::IsDragMode](../Topic/CPane::IsDragMode.md)|Gibt an, ob der Bereich gezogen wird.|  
|[CPane::IsInFloatingMultiPaneFrameWnd](../Topic/CPane::IsInFloatingMultiPaneFrameWnd.md)|Gibt an, ob der Bereich in einem Rahmenfenster mit mehreren Bereichen ist.  \(Überschreibungen `CBasePane::IsInFloatingMultiPaneFrameWnd`.\)|  
|[CPane::IsLeftOf](../Topic/CPane::IsLeftOf.md)|Bestimmt, ob der Bereich \(oder oben\) aus dem angegebenen Rechteck fehlgeschlagen ist.|  
|[CPane::IsResizable](../Topic/CPane::IsResizable.md)|Bestimmt, ob der Bereich angepasst werden kann.  \(Überschreibungen [CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md).\)|  
|[CPane::IsTabbed](../Topic/CPane::IsTabbed.md)|Bestimmt, ob der Bereich in das Tab\-Steuerelement eines Fensters im Registerkartenformat eingefügt wurde.  \(Überschreibungen [CBasePane::IsTabbed](../Topic/CBasePane::IsTabbed.md).\)|  
|[CPane::LoadState](../Topic/CPane::LoadState.md)|Lädt den Zustand des Bereichs aus der Registrierung.  \(Überschreibungen [CBasePane::LoadState](../Topic/CBasePane::LoadState.md).\)|  
|[CPane::MoveByAlignment](../Topic/CPane::MoveByAlignment.md)|Verschiebt den Bereich und das virtuelle Rechteck von der angegebenen Menge.|  
|[CPane::MovePane](../Topic/CPane::MovePane.md)|Verschiebt den Bereich auf das angegebene Rechteck.|  
|[CPane::OnAfterChangeParent](../Topic/CPane::OnAfterChangeParent.md)|Aufgerufen vom Framework, wenn das übergeordnete Element eines Bereichs geändert hat.|  
|[CPane::OnBeforeChangeParent](../Topic/CPane::OnBeforeChangeParent.md)|Aufgerufen vom Framework, wenn das übergeordnete Element des Bereichs im Begriff ist zu ändern.|  
|[CPane::OnPressCloseButton](../Topic/CPane::OnPressCloseButton.md)|Aufgerufen vom Framework, wenn der Benutzer die Schaltfläche Schließen auf der Beschriftung für den Bereich auswählen.|  
|`CPane::OnProcessDblClk`|Wird intern verwendet.|  
|[CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md)|Aufgerufen vom Framework, wenn ein bestimmtes Bereichsmenü im Begriff ist angezeigt werden.|  
|[CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md)|Aufgerufen vom Framework, wenn ein bestimmtes Bereichsmenü im Begriff ist angezeigt werden.|  
|`CPane::PrepareToDock`|Wird intern verwendet.|  
|[CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md)|Berechnet Layoutinformationen für den Bereich neu.  \(Überschreibungen [CBasePane::RecalcLayout](../Topic/CBasePane::RecalcLayout.md).\)|  
|[CPane::SaveState](../Topic/CPane::SaveState.md)|Rettet den Zustand des Bereichs in die Registrierung.  \(Überschreibungen [CBasePane::SaveState](../Topic/CBasePane::SaveState.md).\)|  
|[CPane::SetActiveInGroup](../Topic/CPane::SetActiveInGroup.md)|Kennzeichnet einen Bereich, als aktiv.|  
|[CPane::SetBorders](../Topic/CPane::SetBorders.md)|Legt die Rahmenwerte des Bereichs fest.|  
|[CPane::SetClientHotSpot](../Topic/CPane::SetClientHotSpot.md)|Legt den Hotspot für den Bereich fest.|  
|[CPane::SetDockState](../Topic/CPane::SetDockState.md)|Stellt Informationen des angedockten Zustand für den Bereich wiederherstellen.|  
|[CPane::SetExclusiveRowMode](../Topic/CPane::SetExclusiveRowMode.md)|Aktiviert oder deaktiviert den exklusiven Zeilenmodus.|  
|[CPane::SetMiniFrameRTC](../Topic/CPane::SetMiniFrameRTC.md)|Legt die Ablaufklasseninformationen für das standardmäßige Minirahmenfenster fest.|  
|[CPane::SetMinSize](../Topic/CPane::SetMinSize.md)|Legt das Minimum fest, dessen Größe für den Bereich zulässig ist.|  
|[CPane::SetVirtualRect](../Topic/CPane::SetVirtualRect.md)|Legt das *virtuelle Rechteck des* Bereichs fest.|  
|[CPane::StretchPaneDeferWndPos](../Topic/CPane::StretchPaneDeferWndPos.md)|Streckt den Bereich vertikal oder horizontal auf Grundlage Andockenformat.|  
|[CPane::ToggleAutoHide](../Topic/CPane::ToggleAutoHide.md)|Schaltet Modus "Automatisches Ausblenden" um.|  
|[CPane::UndockPane](../Topic/CPane::UndockPane.md)|Entfernt den Bereich von der Docksite, vom Standardwert Schieberegler oder vom Minirahmenfenster, in dem er gerade angedockt ist.  \(Überschreibungen [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md).\)|  
|[CPane::UpdateVirtualRect](../Topic/CPane::UpdateVirtualRect.md)|Aktualisiert das virtuelle Rechteck.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPane::OnAfterDock](../Topic/CPane::OnAfterDock.md)|Aufgerufen vom Framework ausgelöst, wenn ein Bereich angedockt wurde.|  
|[CPane::OnAfterFloat](../Topic/CPane::OnAfterFloat.md)|Aufgerufen vom Framework ausgelöst, wenn ein Bereich angedockt wurde.|  
|[CPane::OnBeforeDock](../Topic/CPane::OnBeforeDock.md)|Aufgerufen vom Framework, wenn der Bereich im Begriff ist angedockt werden.|  
|[CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md)|Aufgerufen vom Framework ausgelöst, wenn ein Bereich im Begriff ist angedockt werden.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPane::m\_bHandleMinSize](../Topic/CPane::m_bHandleMinSize.md)|Aktiviert konsistente Behandlung der minimale Größe für Bereiche.|  
|[CPane::m\_recentDockInfo](../Topic/CPane::m_recentDockInfo.md)|Enthält neue andockbare Informationen.|  
  
## Hinweise  
 In der Regel werden `CPane`\-Objekte nicht direkt instanziiert.  Wenn Sie einen Bereich benötigen, der andockbare Funktionalität verfügt, leiten Sie das Objekt von [CDockablePane](../../mfc/reference/cdockablepane-class.md).  Wenn Sie anspruchsvolle Symbolleistenfeatures mit einheitlichem benötigen, leiten Sie das Objekt von [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).  
  
 Wenn Sie eine Klasse von `CPane` ableiten, kann es in [CDockSite](../../mfc/reference/cdocksite-class.md) angedockt werden und kann in [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) angedockt werden.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
## Anforderungen  
 **Header:** afxPane.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CBasePane Class](../../mfc/reference/cbasepane-class.md)