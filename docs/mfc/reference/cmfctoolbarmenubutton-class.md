---
title: "CMFCToolBarMenuButton Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarMenuButton class"
ms.assetid: cfa50176-7e4b-4527-9904-86a1b48fc1bc
caps.latest.revision: 31
caps.handback.revision: "19"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarMenuButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Symbolleistenschaltfläche, die ein Popupmenü enthält.  
  
## Syntax  
  
```  
class CMFCToolBarMenuButton : public CMFCToolBarButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CMFCToolBarMenuButton](../Topic/CMFCToolBarMenuButton::CMFCToolBarMenuButton.md)|Erstellt ein `CMFCToolBarMenuButton`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CompareWith](../Topic/CMFCToolBarMenuButton::CompareWith.md)|Vergleicht diese Instanz mit dem angegebenen `CMFCToolBarButton`\-Objekt.  \(Überschreibungen [CMFCToolBarButton::CompareWith](../Topic/CMFCToolBarButton::CompareWith.md).\)|  
|[CMFCToolBarMenuButton::CopyFrom](../Topic/CMFCToolBarMenuButton::CopyFrom.md)|Kopiert die Eigenschaften einer anderen Symbolleisten\-Schaltfläche zur aktuellen Schaltfläche.  \(Überschreibungen [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md).\)|  
|[CMFCToolBarMenuButton::CreateFromMenu](../Topic/CMFCToolBarMenuButton::CreateFromMenu.md)|Initialisiert das Symbolleistenmenü aus einem Menü Fenster\-Handle.|  
|[CMFCToolBarMenuButton::CreateMenu](../Topic/CMFCToolBarMenuButton::CreateMenu.md)|Erstellt ein Menü Fenster, das aus den Befehlen im Symbolleistenmenü besteht.  Gibt ein Handle für das Menü Fenster zurück.|  
|[CMFCToolBarMenuButton::CreatePopupMenu](../Topic/CMFCToolBarMenuButton::CreatePopupMenu.md)|Erstellt ein Popupmenüobjekt \([CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)\) das Symbolleistenmenü anzuzeigen.|  
|[CMFCToolBarMenuButton::EnableQuickCustomize](../Topic/CMFCToolBarMenuButton::EnableQuickCustomize.md)||  
|[CMFCToolBarMenuButton::GetCommands](../Topic/CMFCToolBarMenuButton::GetCommands.md)|Gibt schreibgeschützten Zugriff auf die Liste von Befehlen im Symbolleistenmenü.|  
|[CMFCToolBarMenuButton::GetImageRect](../Topic/CMFCToolBarMenuButton::GetImageRect.md)|Ruft das umschließende Rechteck für das Schaltflächensymbol ab.|  
|[CMFCToolBarMenuButton::GetPaletteRows](../Topic/CMFCToolBarMenuButton::GetPaletteRows.md)|Gibt die Anzahl der Zeilen im Popupmenü zurück, wenn das Menü im Palettenmodus ist.|  
|[CMFCToolBarMenuButton::GetPopupMenu](../Topic/CMFCToolBarMenuButton::GetPopupMenu.md)|Gibt einen Zeiger auf Popupmenüobjekt zurück, das mit der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarMenuButton::HasButton](../Topic/CMFCToolBarMenuButton::HasButton.md)||  
|[CMFCToolBarMenuButton::HaveHotBorder](../Topic/CMFCToolBarMenuButton::HaveHotBorder.md)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt.  \(Überschreibungen [CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md).\)|  
|[CMFCToolBarMenuButton::IsBorder](../Topic/CMFCToolBarMenuButton::IsBorder.md)||  
|[CMFCToolBarMenuButton::IsClickedOnMenu](../Topic/CMFCToolBarMenuButton::IsClickedOnMenu.md)||  
|[CMFCToolBarMenuButton::IsDroppedDown](../Topic/CMFCToolBarMenuButton::IsDroppedDown.md)|Bestimmt, ob das Kontextmenü angezeigt wird.|  
|[CMFCToolBarMenuButton::IsEmptyMenuAllowed](../Topic/CMFCToolBarMenuButton::IsEmptyMenuAllowed.md)|Aufgerufen vom Framework, um zu ermitteln, ob ein Benutzer ein Untermenü vom ausgewählten Menüelement öffnen kann.|  
|[CMFCToolBarMenuButton::IsExclusive](../Topic/CMFCToolBarMenuButton::IsExclusive.md)|Bestimmt, ob die Schaltfläche im exklusiven Modus h. ob ist das Kontextmenü geöffnet bleibt, selbst wenn der Benutzer den Zeiger über einen anderen Symbolleiste oder Schaltfläche bewegt.|  
|[CMFCToolBarMenuButton::IsMenuPaletteMode](../Topic/CMFCToolBarMenuButton::IsMenuPaletteMode.md)|Bestimmt, ob das Kontextmenü im Palettenmodus ist.|  
|[CMFCToolBarMenuButton::IsQuickMode](../Topic/CMFCToolBarMenuButton::IsQuickMode.md)||  
|[CMFCToolBarMenuButton::IsTearOffMenu](../Topic/CMFCToolBarMenuButton::IsTearOffMenu.md)|Bestimmt, ob das Kontextmenü eine Tearoffe Leiste hat.|  
|[CMFCToolBarMenuButton::OnAfterCreatePopupMenu](../Topic/CMFCToolBarMenuButton::OnAfterCreatePopupMenu.md)||  
|[CMFCToolBarMenuButton::OnBeforeDrag](../Topic/CMFCToolBarMenuButton::OnBeforeDrag.md)|Gibt an, ob die Schaltfläche gezogen werden können.  \(Überschreibungen [CMFCToolBarButton::OnBeforeDrag](../Topic/CMFCToolBarButton::OnBeforeDrag.md).\)|  
|[CMFCToolBarMenuButton::OnCalculateSize](../Topic/CMFCToolBarMenuButton::OnCalculateSize.md)|Aufgerufen vom Framework, um die Größe der Schaltfläche für den angegebenen Gerätekontext und den angedockten Zustand zu berechnen.  \(Überschreibungen [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md).\)|  
|[CMFCToolBarMenuButton::OnCancelMode](../Topic/CMFCToolBarMenuButton::OnCancelMode.md)|Aufgerufen vom Framework, um die [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) Meldung zu bearbeiten.  \(Überschreibungen [CMFCToolBarButton::OnCancelMode](../Topic/CMFCToolBarButton::OnCancelMode.md).\)|  
|[CMFCToolBarMenuButton::OnChangeParentWnd](../Topic/CMFCToolBarMenuButton::OnChangeParentWnd.md)|Aufgerufen vom Framework, wenn die Schaltfläche in eine neue Symbolleiste eingefügt wird.  \(Überschreibungen [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md).\)|  
|[CMFCToolBarMenuButton::OnClick](../Topic/CMFCToolBarMenuButton::OnClick.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Maustaste klickt.  \(Überschreibungen [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md).\)|  
|[CMFCToolBarMenuButton::OnClickMenuItem](../Topic/CMFCToolBarMenuButton::OnClickMenuItem.md)|Aufgerufen vom Framework, wenn der Benutzer ein Element im Popupmenü auswählt.|  
|[CMFCToolBarMenuButton::OnContextHelp](../Topic/CMFCToolBarMenuButton::OnContextHelp.md)|Aufgerufen vom Framework, wenn die Elemente eine Symbolleiste `WM_HELPHITTEST` Meldung verarbeitet.  \(Überschreibungen [CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md).\)|  
|[CMFCToolBarMenuButton::OnDraw](../Topic/CMFCToolBarMenuButton::OnDraw.md)|Aufgerufen durch das Framework, um die Schaltfläche mithilfe der angegebenen Formate und der Optionen zu zeichnen.  \(Überschreibungen [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md).\)|  
|[CMFCToolBarMenuButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarMenuButton::OnDrawOnCustomizeList.md)|Aufgerufen durch das Framework, um die Schaltfläche im Bereich **Befehle** des Dialogfelds **Anpassen** zu zeichnen.  \(Überschreibungen [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md).\)|  
|[CMFCToolBarMenuButton::OpenPopupMenu](../Topic/CMFCToolBarMenuButton::OpenPopupMenu.md)|Aufgerufen vom Framework, wenn der Benutzer das Popupmenü öffnet.|  
|[CMFCToolBarMenuButton::ResetImageToDefault](../Topic/CMFCToolBarMenuButton::ResetImageToDefault.md)|Legt den Standardwert das Bild fest, das der Schaltfläche zugeordnet ist.  \(Überschreibungen [CMFCToolBarButton::ResetImageToDefault](../Topic/CMFCToolBarButton::ResetImageToDefault.md).\)|  
|[CMFCToolBarMenuButton::SaveBarState](../Topic/CMFCToolBarMenuButton::SaveBarState.md)|Rettet den Zustand der Symbolleisten\-Schaltfläche.  \(Überschreibungen [CMFCToolBarButton::SaveBarState](../Topic/CMFCToolBarButton::SaveBarState.md).\)|  
|[CMFCToolBarMenuButton::Serialize](../Topic/CMFCToolBarMenuButton::Serialize.md)|Liest dieses Objekt einem Archiv oder schreibt es einem Archiv.  \(Überschreibungen [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md).\)|  
|[CMFCToolBarMenuButton::SetACCData](../Topic/CMFCToolBarMenuButton::SetACCData.md)|Füllt das bereitgestellte `CAccessibilityData`\-Objekt mit Barrierefreiheitsdaten von der Symbolleisten\-Schaltfläche auf.  \(Überschreibungen [CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md).\)|  
|[CMFCToolBarMenuButton::SetMenuOnly](../Topic/CMFCToolBarMenuButton::SetMenuOnly.md)|Gibt an, ob die Schaltfläche zu einer Symbolleiste hinzugefügt werden kann.|  
|[CMFCToolBarMenuButton::SetMenuPaletteMode](../Topic/CMFCToolBarMenuButton::SetMenuPaletteMode.md)|Gibt an, ob das Kontextmenü im Palettenmodus ist.|  
|[CMFCToolBarMenuButton::SetMessageWnd](../Topic/CMFCToolBarMenuButton::SetMessageWnd.md)||  
|[CMFCToolBarMenuButton::SetRadio](../Topic/CMFCToolBarMenuButton::SetRadio.md)|Erzwingt die Symbolleistenmenüschaltfläche, um ein Symbol anzuzeigen, dass es ausgewählt wird.|  
|[CMFCToolBarMenuButton::SetTearOff](../Topic/CMFCToolBarMenuButton::SetTearOff.md)|Gibt eine Tearoffe Leiste ID für das Kontextmenü an.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::DrawDocumentIcon](../Topic/CMFCToolBarMenuButton::DrawDocumentIcon.md)|Zeichnet ein Symbol auf der Menüschaltfläche.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::m\_bAlwaysCallOwnerDraw](../Topic/CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw.md)|Wenn `TRUE`, das Framework immer [CFrameWndEx::OnDrawMenuImage](../Topic/CFrameWndEx::OnDrawMenuImage.md) aufruft, wenn eine Schaltfläche gezeichnet wird.|  
  
## Hinweise  
 `CMFCToolBarMenuButton` kann als Menü, Menüelement, das ein Untermenü, eine Schaltfläche, der hat entweder einen Befehl ausführt oder ein Menü anzeigt, oder Schaltfläche angezeigt werden, die nur ein Menü angezeigt.  Sie legen das Verhalten und die Darstellung der Menüschaltfläche, indem Sie Parameter wie das Bild, der Text, das Menühandle und die Befehls\-ID angeben, die mit der Schaltfläche im Konstruktor `CMFCToolbarMenuButton::CMFCToolbarMenuButton` zugeordnet ist.  
  
 Eine benutzerdefinierte Klasse, die von der `CMFCToolbarMenuButton`\-Klasse abgeleitet ist, muss das [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md)\-Makro verwenden.  Das [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md)\-Makro generiert einen Fehler, wenn die Anwendung geschlossen wird.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt `CMFCToolBarMenuButton` konfiguriert.  Im Code wird veranschaulicht, wie Sie, dass das Dropdownmenü ist im Palettenmodus, und die ID für die Tearoffe Leiste angibt, angibt, die erstellt wird, wenn der Benutzer die Menütaste weg einer Menüleiste zieht.  Dieser Codeausschnitt ist Teil [Word\-Auflagenbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_WordPad#10](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_WordPad#10)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
## Anforderungen  
 **Header:** afxtoolbarmenubutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)