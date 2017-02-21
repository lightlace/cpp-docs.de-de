---
title: "CMFCPopupMenu Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPopupMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPopupMenu class"
ms.assetid: 9555dca1-8c9c-44c9-af72-0659ddad128e
caps.latest.revision: 40
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 42
---
# CMFCPopupMenu Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Werkzeug\-Windows\-Popupmenüfunktionalität und erweitert, indem sie sie Funktionen wie Tearoffe Menüs und QuickInfos hinzugefügt wird.  
  
## Syntax  
  
```  
class CMFCPopupMenu : public CMiniFrameWnd  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPopupMenu::CMFCPopupMenu](../Topic/CMFCPopupMenu::CMFCPopupMenu.md)|Erstellt ein `CMFCPopupMenu`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPopupMenu::ActivatePopupMenu](../Topic/CMFCPopupMenu::ActivatePopupMenu.md)||  
|[CMFCPopupMenu::AlwaysShowEmptyToolsEntry](../Topic/CMFCPopupMenu::AlwaysShowEmptyToolsEntry.md)|Legt fest, ob ein Popupmenü aktiviert ist, um leere Einträge für benutzerdefinierte Tools anzeigen.|  
|[CMFCPopupMenu::AreAllCommandsShown](../Topic/CMFCPopupMenu::AreAllCommandsShown.md)||  
|[CMFCPopupMenu::CheckArea](../Topic/CMFCPopupMenu::CheckArea.md)|Bestimmt den Speicherort eines Punkts relativ zum Popupmenü.|  
|[CMFCPopupMenu::CloseMenu](../Topic/CMFCPopupMenu::CloseMenu.md)||  
|[CMFCPopupMenu::Create](../Topic/CMFCPopupMenu::Create.md)|Erstellt ein Popupmenü und fügt es dem `CMFCPopupMenu`\-Objekt.|  
|[CMFCPopupMenu::DefaultMouseClickOnClose](../Topic/CMFCPopupMenu::DefaultMouseClickOnClose.md)||  
|[CMFCPopupMenu::EnableMenuLogo](../Topic/CMFCPopupMenu::EnableMenuLogo.md)|Initialisiert das Logo für ein Popupmenü.|  
|[CMFCPopupMenu::EnableMenuSound](../Topic/CMFCPopupMenu::EnableMenuSound.md)|Ermöglicht Menüsound.|  
|[CMFCPopupMenu::EnableResize](../Topic/CMFCPopupMenu::EnableResize.md)||  
|[CMFCPopupMenu::EnableScrolling](../Topic/CMFCPopupMenu::EnableScrolling.md)||  
|[CMFCPopupMenu::EnableVertResize](../Topic/CMFCPopupMenu::EnableVertResize.md)||  
|[CMFCPopupMenu::FindSubItemByCommand](../Topic/CMFCPopupMenu::FindSubItemByCommand.md)||  
|[CMFCPopupMenu::GetActiveMenu](../Topic/CMFCPopupMenu::GetActiveMenu.md)|Gibt das aktuell aktive Menü zurück.|  
|[CMFCPopupMenu::GetAnimationSpeed](../Topic/CMFCPopupMenu::GetAnimationSpeed.md)|Gibt die Animationsgeschwindigkeit für Popupmenüs zurück.|  
|[CMFCPopupMenu::GetAnimationType](../Topic/CMFCPopupMenu::GetAnimationType.md)|Gibt den aktuellen Typ der Popupmenüanimation zurück.|  
|[CMFCPopupMenu::GetDropDirection](../Topic/CMFCPopupMenu::GetDropDirection.md)||  
|[CMFCPopupMenu::GetForceMenuFocus](../Topic/CMFCPopupMenu::GetForceMenuFocus.md)|Gibt an, ob der Fokus der Menüleiste zurückgegeben wird, wenn ein Popupmenü angezeigt wird.|  
|[CMFCPopupMenu::GetForceShadow](../Topic/CMFCPopupMenu::GetForceShadow.md)||  
|[CMFCPopupMenu::GetHMenu](../Topic/CMFCPopupMenu::GetHMenu.md)|Gibt ein Handle zur angefügten Menüressource zurück.|  
|[CMFCPopupMenu::GetMenuBar](../Topic/CMFCPopupMenu::GetMenuBar.md)|Gibt [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) zurück, das innerhalb des Popupmenüs eingebettet ist.|  
|[CMFCPopupMenu::GetMenuItem](../Topic/CMFCPopupMenu::GetMenuItem.md)|Gibt einen Zeiger auf das Menüelement am angegebenen Index zurück.|  
|[CMFCPopupMenu::GetMenuItemCount](../Topic/CMFCPopupMenu::GetMenuItemCount.md)|Gibt die Anzahl der Elemente in einem Popupmenü zurück.|  
|[CMFCPopupMenu::GetMessageWnd](../Topic/CMFCPopupMenu::GetMessageWnd.md)|Gibt einen Zeiger auf das Fenster zurück, in dem das Framework die Popupmenümeldungen weiterleitet.|  
|[CMFCPopupMenu::GetParentArea](../Topic/CMFCPopupMenu::GetParentArea.md)||  
|[CMFCPopupMenu::GetParentButton](../Topic/CMFCPopupMenu::GetParentButton.md)|Gibt einen Zeiger auf die Symbolleistenschaltfläche Elementen zurück.|  
|[CMFCPopupMenu::GetParentPopupMenu](../Topic/CMFCPopupMenu::GetParentPopupMenu.md)|Gibt einen Zeiger auf Elementen Popupmenü zurück.|  
|[CMFCPopupMenu::GetParentRibbonElement](../Topic/CMFCPopupMenu::GetParentRibbonElement.md)||  
|[CMFCPopupMenu::GetParentToolBar](../Topic/CMFCPopupMenu::GetParentToolBar.md)|Gibt einen Zeiger auf die Elemente Symbolleiste zurück.|  
|[CMFCPopupMenu::GetQuickCustomizeType](../Topic/CMFCPopupMenu::GetQuickCustomizeType.md)||  
|[CMFCPopupMenu::GetSelItem](../Topic/CMFCPopupMenu::GetSelItem.md)|Gibt einen Zeiger auf den aktuell ausgewählten Menübefehl zurück.|  
|[CMFCPopupMenu::HasBeenResized](../Topic/CMFCPopupMenu::HasBeenResized.md)||  
|[CMFCPopupMenu::HideRarelyUsedCommands](../Topic/CMFCPopupMenu::HideRarelyUsedCommands.md)|Gibt an, ob das Popupmenü selten verwendete Befehle ausblenden kann.|  
|[CMFCPopupMenu::InCommand](../Topic/CMFCPopupMenu::InCommand.md)||  
|[CMFCPopupMenu::InsertItem](../Topic/CMFCPopupMenu::InsertItem.md)|Fügt ein neues Element in das Kontextmenü an der angegebenen Position ein.|  
|[CMFCPopupMenu::InsertSeparator](../Topic/CMFCPopupMenu::InsertSeparator.md)|Fügt ein Trennzeichen in das Kontextmenü an der angegebenen Position ein.|  
|[CMFCPopupMenu::IsAlwaysClose](../Topic/CMFCPopupMenu::IsAlwaysClose.md)||  
|[CMFCPopupMenu::IsAlwaysShowEmptyToolsEntry](../Topic/CMFCPopupMenu::IsAlwaysShowEmptyToolsEntry.md)||  
|[CMFCPopupMenu::IsCustomizePane](../Topic/CMFCPopupMenu::IsCustomizePane.md)|Gibt an, ob das Popupmenü als **QuickCustomizePane** funktioniert.|  
|[CMFCPopupMenu::IsEscClose](../Topic/CMFCPopupMenu::IsEscClose.md)||  
|[CMFCPopupMenu::IsIdle](../Topic/CMFCPopupMenu::IsIdle.md)|Gibt an, ob ein Popupmenü derzeit im Leerlauf befindet.|  
|[CMFCPopupMenu::IsMenuSound](../Topic/CMFCPopupMenu::IsMenuSound.md)||  
|[CMFCPopupMenu::IsQuickCustomize](../Topic/CMFCPopupMenu::IsQuickCustomize.md)|Bestimmt, ob zugeordnete [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md) in QuickCustomize\-Modus ist.|  
|[CMFCPopupMenu::IsResizeble](../Topic/CMFCPopupMenu::IsResizeble.md)||  
|[CMFCPopupMenu::IsRightAlign](../Topic/CMFCPopupMenu::IsRightAlign.md)|Gibt an, ob das Menü rechtsbündig oder linksbündig ist.|  
|[CMFCPopupMenu::IsScrollable](../Topic/CMFCPopupMenu::IsScrollable.md)||  
|[CMFCPopupMenu::IsSendMenuSelectMsg](../Topic/CMFCPopupMenu::IsSendMenuSelectMsg.md)|Gibt an, ob das Framework die übergeordneten Frames benachrichtigt, wenn der Benutzer einen Befehl im Popupmenü auswählt.|  
|[CMFCPopupMenu::IsShown](../Topic/CMFCPopupMenu::IsShown.md)|Gibt an, ob das Popupmenü gerade sichtbar ist.|  
|[CMFCPopupMenu::MoveTo](../Topic/CMFCPopupMenu::MoveTo.md)||  
|[CMFCPopupMenu::OnCmdMsg](../Topic/CMFCPopupMenu::OnCmdMsg.md)|\(Überschreibungen `CFrameWnd::OnCmdMsg`.\)|  
|[CMFCPopupMenu::PostCommand](../Topic/CMFCPopupMenu::PostCommand.md)||  
|[CMFCPopupMenu::PreTranslateMessage](../Topic/CMFCPopupMenu::PreTranslateMessage.md)|\(Überschreibungen `CFrameWnd::PreTranslateMessage`.\)|  
|[CMFCPopupMenu::RecalcLayout](../Topic/CMFCPopupMenu::RecalcLayout.md)|Aufgerufen vom Framework, wenn die Standardsteuerelementleisten umgeschaltetes oder deaktiviert sind, oder wenn das Rahmenfenster angepasst wird.  \(Überschreibungen [CFrameWnd::RecalcLayout](../Topic/CFrameWnd::RecalcLayout.md).\)|  
|[CMFCPopupMenu::RemoveAllItems](../Topic/CMFCPopupMenu::RemoveAllItems.md)|Löscht alle Elemente aus einem Popupmenü.|  
|[CMFCPopupMenu::RemoveItem](../Topic/CMFCPopupMenu::RemoveItem.md)|Entfernt das angegebene Element aus einem Popupmenü.|  
|[CMFCPopupMenu::SaveState](../Topic/CMFCPopupMenu::SaveState.md)||  
|[CMFCPopupMenu::SetAnimationSpeed](../Topic/CMFCPopupMenu::SetAnimationSpeed.md)|Legt die Animationsgeschwindigkeit für Popupmenüs fest.|  
|[CMFCPopupMenu::SetAnimationType](../Topic/CMFCPopupMenu::SetAnimationType.md)|Legt den Animationstyp für das Kontextmenü fest.|  
|[CMFCPopupMenu::SetAutoDestroy](../Topic/CMFCPopupMenu::SetAutoDestroy.md)||  
|[CMFCPopupMenu::SetDefaultItem](../Topic/CMFCPopupMenu::SetDefaultItem.md)|Legt den Standardbefehl für das Kontextmenü fest.|  
|[CMFCPopupMenu::SetForceMenuFocus](../Topic/CMFCPopupMenu::SetForceMenuFocus.md)|Erzwingt den Eingabefokus, um zur Menüleiste zurückzukehren, wenn ein Popupmenü angezeigt wird.|  
|[CMFCPopupMenu::SetForceShadow](../Topic/CMFCPopupMenu::SetForceShadow.md)|Erzwingt das Framework, um Menüschatten zu zeichnen, wenn Popupmenüs außerhalb des Großrechners angezeigt werden.|  
|[CMFCPopupMenu::SetMaxWidth](../Topic/CMFCPopupMenu::SetMaxWidth.md)|Legen Sie die maximale Breite für das Kontextmenü fest.|  
|[CMFCPopupMenu::SetMessageWnd](../Topic/CMFCPopupMenu::SetMessageWnd.md)||  
|[CMFCPopupMenu::SetParentRibbonElement](../Topic/CMFCPopupMenu::SetParentRibbonElement.md)||  
|[CMFCPopupMenu::SetQuickCustomizeType](../Topic/CMFCPopupMenu::SetQuickCustomizeType.md)||  
|[CMFCPopupMenu::SetQuickMode](../Topic/CMFCPopupMenu::SetQuickMode.md)||  
|[CMFCPopupMenu::SetRightAlign](../Topic/CMFCPopupMenu::SetRightAlign.md)|Legt die Menüausrichtung für Popupmenüs fest.|  
|[CMFCPopupMenu::SetSendMenuSelectMsg](../Topic/CMFCPopupMenu::SetSendMenuSelectMsg.md)|Legt ein Flag fest, das steuert, ob das Popupmenü seine übergeordneten Frames benachrichtigt, wenn der Benutzer einen Befehl auswählt.|  
|[CMFCPopupMenu::ShowAllCommands](../Topic/CMFCPopupMenu::ShowAllCommands.md)|Erzwingt das Kontextmenü, um alle Befehle anzuzeigen.|  
|[CMFCPopupMenu::TriggerResize](../Topic/CMFCPopupMenu::TriggerResize.md)||  
|[CMFCPopupMenu::UpdateAllShadows](../Topic/CMFCPopupMenu::UpdateAllShadows.md)|Aktualisiert die Schatten für alle geöffneten Popupmenüs.|  
|[CMFCPopupMenu::UpdateShadow](../Topic/CMFCPopupMenu::UpdateShadow.md)|Aktualisiert den Schatten für das Popupmenü.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPopupMenu::CreateTearOffBar](../Topic/CMFCPopupMenu::CreateTearOffBar.md)||  
|[CMFCPopupMenu::OnChangeHot](../Topic/CMFCPopupMenu::OnChangeHot.md)||  
|[CMFCPopupMenu::OnChooseItem](../Topic/CMFCPopupMenu::OnChooseItem.md)||  
  
### Hinweise  
 Normalerweise erstellt MFC Popupmenüs automatisch.  Wenn Sie ein Objekt `CMFCPopupMenu` manuell erstellen möchten, ordnen Sie ein auf dem Heap zu und rufen Sie dann [CMFCPopupMenu::Create](../Topic/CMFCPopupMenu::Create.md) auf.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Popupmenüobjekt konfiguriert.  Im Beispiel wird gezeigt, wie das Logo und den Sound des Popupmenüs festlegen, die Animationsgeschwindigkeit und den Typ, zeichnen Menüschatten festlegt, wenn das Popupmenü außerhalb des Großrechners angezeigt wird, die maximale Breite festgelegt und die rechte Menüausrichtung des Popupmenüs fest.  Dieser Codeausschnitt ist Teil [Gewohnheits\-Seitenbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_CustomPages#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_CustomPages#2)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
## Anforderungen  
 **Header:** afxpopupmenu.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenuBar\-Klasse](../../mfc/reference/cmfcpopupmenubar-class.md)