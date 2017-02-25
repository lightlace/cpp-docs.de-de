---
title: "CMFCToolBarButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarButton class"
ms.assetid: 8a6ecffb-86b0-4f5c-8211-a9146b463efd
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# CMFCToolBarButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt Schaltflächenfunktionalität auf Symbolleisten bereit.  
  
## Syntax  
  
```  
class CMFCToolBarButton : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarButton::CMFCToolBarButton](../Topic/CMFCToolBarButton::CMFCToolBarButton.md)|erstellt und initialisiert ein `CMFCToolBarButton`\-Objekt.|  
|`CMFCToolBarButton::~CMFCToolBarButton`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarButton::CanBeDropped](../Topic/CMFCToolBarButton::CanBeDropped.md)|Gibt an, ob ein Benutzer eine Schaltfläche auf einer Symbolleiste oder einem Menü während der Anpassung positionieren kann.|  
|[CMFCToolBarButton::CanBeStored](../Topic/CMFCToolBarButton::CanBeStored.md)|Gibt an, ob die Schaltfläche gespeichert werden kann.|  
|[CMFCToolBarButton::CanBeStretched](../Topic/CMFCToolBarButton::CanBeStretched.md)|Gibt an, ob ein Benutzer die Schaltfläche während der Anpassung strecken kann.|  
|[CMFCToolBarButton::CompareWith](../Topic/CMFCToolBarButton::CompareWith.md)|Vergleicht diese Instanz mit dem angegebenen `CMFCToolBarButton`\-Objekt.|  
|[CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md)|Kopiert die Eigenschaften einer anderen Symbolleisten\-Schaltfläche zur aktuellen Schaltfläche.|  
|[CMFCToolBarButton::CreateFromOleData](../Topic/CMFCToolBarButton::CreateFromOleData.md)|Erstellt ein Objekt `CMFCToolBarButton` im bereitgestellten `COleDataObject`\-Objekt.|  
|`CMFCToolBarButton::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCToolBarButton::EnableWindow](../Topic/CMFCToolBarButton::EnableWindow.md)|Aktiviert oder deaktiviert Maus\- und Tastatureingaben.|  
|[CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md)|Kopien Text aus der Symbolleisten\-Schaltfläche zu einem Menü.|  
|[CMFCToolBarButton::GetClipboardFormat](../Topic/CMFCToolBarButton::GetClipboardFormat.md)|Ruft das globale Zwischenablageformat für die Anwendung ab.|  
|[CMFCToolBarButton::GetHwnd](../Topic/CMFCToolBarButton::GetHwnd.md)|Ruft das Fensterhandle ab, das der Symbolleisten\-Schaltfläche zugeordnet ist.|  
|[CMFCToolBarButton::GetImage](../Topic/CMFCToolBarButton::GetImage.md)|Ruft den Bildindex der Schaltfläche ab.|  
|[CMFCToolBarButton::GetInvalidateRect](../Topic/CMFCToolBarButton::GetInvalidateRect.md)|Ruft den des Innenbereichs der Schaltfläche ab, die neu gezeichnet werden muss.|  
|[CMFCToolBarButton::GetParentWnd](../Topic/CMFCToolBarButton::GetParentWnd.md)|Ruft das übergeordnete Fenster der Schaltfläche ab.|  
|[CMFCToolBarButton::GetProtectedCommands](../Topic/CMFCToolBarButton::GetProtectedCommands.md)|Ruft die Liste von Befehlen ab, die der Benutzer nicht anpassen kann.|  
|[CMFCToolBarButton::GetTextSize](../Topic/CMFCToolBarButton::GetTextSize.md)|Ruft die Größe des Schaltflächentexts ab.|  
|[CMFCToolBarButton::HasFocus](../Topic/CMFCToolBarButton::HasFocus.md)|Bestimmt, ob die Schaltfläche den aktuellen Eingabefokus hat.|  
|[CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt.|  
|[CMFCToolBarButton::IsDrawImage](../Topic/CMFCToolBarButton::IsDrawImage.md)|Bestimmt, ob ein Bild auf der Schaltfläche angezeigt wird.|  
|[CMFCToolBarButton::IsDrawText](../Topic/CMFCToolBarButton::IsDrawText.md)|Bestimmt, ob eine Beschriftung auf der Schaltfläche angezeigt wird.|  
|[CMFCToolBarButton::IsDroppedDown](../Topic/CMFCToolBarButton::IsDroppedDown.md)|Bestimmt, ob die Schaltfläche ein Untermenü anzeigt.|  
|[CMFCToolBarButton::IsEditable](../Topic/CMFCToolBarButton::IsEditable.md)|Bestimmt, ob die Schaltfläche angepasst werden kann.|  
|[CMFCToolBarButton::IsExtraSize](../Topic/CMFCToolBarButton::IsExtraSize.md)|Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann.|  
|[CMFCToolBarButton::IsFirstInGroup](../Topic/CMFCToolBarButton::IsFirstInGroup.md)|Bestimmt, ob die Schaltfläche an der ersten Position in einer Schaltflächengruppe ist.|  
|[CMFCToolBarButton::IsHidden](../Topic/CMFCToolBarButton::IsHidden.md)|Bestimmt, ob die Schaltfläche ausgeblendet wird.|  
|[CMFCToolBarButton::IsHorizontal](../Topic/CMFCToolBarButton::IsHorizontal.md)|Bestimmt, ob die Schaltfläche auf einer horizontalen Symbolleiste ist.|  
|[CMFCToolBarButton::IsLastInGroup](../Topic/CMFCToolBarButton::IsLastInGroup.md)|Gibt an, ob die Schaltfläche in der letzten Position in einer Schaltflächengruppe ist.|  
|[CMFCToolBarButton::IsLocked](../Topic/CMFCToolBarButton::IsLocked.md)|Bestimmt, ob die Schaltfläche auf einer gesperrten \(nicht\-vomBenutzer anpassbare Symbolleiste\) ist.|  
|[CMFCToolBarButton::IsOwnerOf](../Topic/CMFCToolBarButton::IsOwnerOf.md)|Bestimmt, ob die Schaltfläche der Besitzer des bereitgestellten Fensterhandles ist.|  
|[CMFCToolBarButton::IsVisible](../Topic/CMFCToolBarButton::IsVisible.md)|Bestimmt, ob die Symbolleistenschaltfläche sichtbar ist.|  
|[CMFCToolBarButton::IsWindowVisible](../Topic/CMFCToolBarButton::IsWindowVisible.md)|Bestimmt, ob das zugrunde liegende Fensterhandle der Schaltfläche sichtbar ist.|  
|[CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md)|Gibt an, ob die Schaltfläche die [Da WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Meldung verarbeitet.|  
|[CMFCToolBarButton::OnAddToCustomizePage](../Topic/CMFCToolBarButton::OnAddToCustomizePage.md)|Aufgerufen vom Framework, wenn die Schaltfläche zu einem Dialogfeld **Anpassen** hinzugefügt wird.|  
|[CMFCToolBarButton::OnBeforeDrag](../Topic/CMFCToolBarButton::OnBeforeDrag.md)|Gibt an, ob die Schaltfläche gezogen werden können.|  
|[CMFCToolBarButton::OnBeforeDrop](../Topic/CMFCToolBarButton::OnBeforeDrop.md)|Gibt an, ob ein Benutzer die Schaltfläche auf die Zielsymbolleiste ablegen kann.|  
|[CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md)|Aufgerufen vom Framework, um die Größe der Schaltfläche für den angegebenen Gerätekontext und den angedockten Zustand zu berechnen.|  
|[CMFCToolBarButton::OnCancelMode](../Topic/CMFCToolBarButton::OnCancelMode.md)|Aufgerufen vom Framework, um die [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) Meldung zu bearbeiten.|  
|[CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md)|Aufgerufen vom Framework, wenn die Schaltfläche in eine neue Symbolleiste eingefügt wird.|  
|[CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Maustaste klickt.|  
|[CMFCToolBarButton::OnClickUp](../Topic/CMFCToolBarButton::OnClickUp.md)|Aufgerufen vom Framework, wenn der Benutzer die Maustaste loslässt.|  
|[CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md)|Aufgerufen vom Framework, wenn die Elemente eine Symbolleiste `WM_HELPHITTEST` Meldung verarbeitet.|  
|[CMFCToolBarButton::OnCtlColor](../Topic/CMFCToolBarButton::OnCtlColor.md)|Aufgerufen vom Framework, wenn die Elemente eine Symbolleiste `WM_CTLCOLOR` Meldung verarbeitet.|  
|[CMFCToolBarButton::OnCustomizeMenu](../Topic/CMFCToolBarButton::OnCustomizeMenu.md)|Ermöglicht der Schaltfläche, um das bereitgestellte Menü zu ändern, wenn die Anwendung ein Kontextmenü auf der übergeordneten Symbolleiste angezeigt wird.|  
|[CMFCToolBarButton::OnDblClk](../Topic/CMFCToolBarButton::OnDblClk.md)|Aufgerufen vom Framework, wenn die Elemente eine Symbolleiste [WM\_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) Meldung verarbeitet.|  
|[CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md)|Aufgerufen durch das Framework, um die Schaltfläche mithilfe der angegebenen Formate und der Optionen zu zeichnen.|  
|[CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md)|Aufgerufen durch das Framework, um die Schaltfläche im Bereich **Befehle** des Dialogfelds **Anpassen** zu zeichnen.|  
|[CMFCToolBarButton::OnGetCustomToolTipText](../Topic/CMFCToolBarButton::OnGetCustomToolTipText.md)|Aufgerufen vom Framework, um den benutzerdefinierten QuickInfo\-Text für die Schaltfläche abzurufen.|  
|[CMFCToolBarButton::OnGlobalFontsChanged](../Topic/CMFCToolBarButton::OnGlobalFontsChanged.md)|Aufgerufen vom Framework, wenn die globale Schriftart geändert hat.|  
|[CMFCToolBarButton::OnMove](../Topic/CMFCToolBarButton::OnMove.md)|Aufgerufen vom Framework, wenn die Elemente Symbolleiste bewegt.|  
|[CMFCToolBarButton::OnShow](../Topic/CMFCToolBarButton::OnShow.md)|Aufgerufen vom Framework, wenn die Schaltfläche sichtbar oder nicht sichtbar ist.|  
|[CMFCToolBarButton::OnSize](../Topic/CMFCToolBarButton::OnSize.md)|Aufgerufen vom Framework, wenn die Elemente Symbolleiste ändert, erfordert die Größe oder Position und diese Änderung die Schaltfläche, ihre Größe ändern.|  
|[CMFCToolBarButton::OnToolHitTest](../Topic/CMFCToolBarButton::OnToolHitTest.md)|Aufgerufen vom Framework, wenn die Elemente Symbolleiste bestimmen muss, ob ein Punkt im umgebenden Rechteck der Schaltfläche ist.|  
|[CMFCToolBarButton::OnUpdateToolTip](../Topic/CMFCToolBarButton::OnUpdateToolTip.md)|Aufgerufen vom Framework, wenn die Elemente Symbolleiste den QuickInfo\-Text aktualisiert.|  
|[CMFCToolBarButton::PrepareDrag](../Topic/CMFCToolBarButton::PrepareDrag.md)|Aufgerufen vom Framework, wenn die Schaltfläche im Begriff ist, einen Drag & Drop\-Vorgang auszuführen.|  
|[CMFCToolBarButton::Rect](../Topic/CMFCToolBarButton::Rect.md)|Ruft das umschließende Rechteck der Schaltfläche ab.|  
|[CMFCToolBarButton::ResetImageToDefault](../Topic/CMFCToolBarButton::ResetImageToDefault.md)|Legt den Standardwert das Bild fest, das der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarButton::SaveBarState](../Topic/CMFCToolBarButton::SaveBarState.md)|Rettet den Zustand der Symbolleisten\-Schaltfläche.|  
|[CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md)|Liest dieses Objekt einem Archiv oder schreibt es einem Archiv.  \(Überschreibungen [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md)|Füllt das bereitgestellte `CAccessibilityData`\-Objekt mit Barrierefreiheitsdaten von der Symbolleisten\-Schaltfläche auf.|  
|[CMFCToolBarButton::SetClipboardFormatName](../Topic/CMFCToolBarButton::SetClipboardFormatName.md)|Benennt das globale Zwischenablageformat.|  
|[CMFCToolBarButton::SetImage](../Topic/CMFCToolBarButton::SetImage.md)|Legt den Bildindex der Schaltfläche fest.|  
|[CMFCToolBarButton::SetProtectedCommands](../Topic/CMFCToolBarButton::SetProtectedCommands.md)|Legt die Liste von Befehlen fest, die der Benutzer nicht anpassen kann.|  
|[CMFCToolBarButton::SetRadio](../Topic/CMFCToolBarButton::SetRadio.md)|Aufgerufen vom Framework, wenn eine Schaltfläche den aktivierten Zustand ändert.|  
|[CMFCToolBarButton::SetRect](../Topic/CMFCToolBarButton::SetRect.md)|Legt das umschließende Rechteck der Schaltfläche fest.|  
|[CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md)|Legt das Format der Schaltfläche fest.|  
|[CMFCToolBarButton::SetVisible](../Topic/CMFCToolBarButton::SetVisible.md)|Gibt an, ob die Schaltfläche sichtbar ist.|  
|[CMFCToolBarButton::Show](../Topic/CMFCToolBarButton::Show.md)|Zeigt die Schaltfläche oder aus.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarButton::m\_bImage](../Topic/CMFCToolBarButton::m_bImage.md)|Gibt an, ob ein Bild auf der Schaltfläche angezeigt wird.|  
|[CMFCToolBarButton::m\_bText](../Topic/CMFCToolBarButton::m_bText.md)|Gibt an, ob eine Beschriftung auf der Schaltfläche angezeigt wird.|  
|[CMFCToolBarButton::m\_bTextBelow](../Topic/CMFCToolBarButton::m_bTextBelow.md)|Gibt an, ob die Beschriftung unter das Bild auf der Schaltfläche angezeigt wird.|  
|[CMFCToolBarButton::m\_bUserButton](../Topic/CMFCToolBarButton::m_bUserButton.md)|Gibt an, ob die Schaltfläche ein benutzerdefiniertes Bild.|  
|[CMFCToolBarButton::m\_bWholeText](../Topic/CMFCToolBarButton::m_bWholeText.md)|Gibt an, ob die Schaltfläche seine Ganztextbezeichnung angezeigt, auch wenn sie nicht in das umschließende Rechteck passt.|  
|[CMFCToolBarButton::m\_bWrap](../Topic/CMFCToolBarButton::m_bWrap.md)|Gibt an, ob die Schaltfläche neben einem Trennzeichen in die nächste Zeile gesetzt wird.|  
|[CMFCToolBarButton::m\_bWrapText](../Topic/CMFCToolBarButton::m_bWrapText.md)|Gibt an, ob Mehrkanalbeschriftungen aktiviert werden.|  
|[CMFCToolBarButton::m\_nID](../Topic/CMFCToolBarButton::m_nID.md)|Die Befehls\-ID der Schaltfläche.|  
|[CMFCToolBarButton::m\_nStyle](../Topic/CMFCToolBarButton::m_nStyle.md)|Das Format der Schaltfläche.|  
|[CMFCToolBarButton::m\_strText](../Topic/CMFCToolBarButton::m_strText.md)|Die Beschriftung der Schaltfläche.|  
  
## Hinweise  
 Ein Objekt `CMFCToolbarButton` ist ein Steuerelement, das auf einer Symbolleiste auf.  Das Verhalten ähnelt dem einer normalen Schaltfläche.  Sie können ein Bild und eine Beschriftung auf dieses Objekt zuweisen.  Eine Symbolleisten\-Schaltfläche kann eine Befehl ID verfügen  Wenn der Benutzer auf die Schaltfläche klickt, führt das Framework den Befehl aus, den diese ID angibt.  
  
 In der Regel können Symbolleisten\-Schaltflächen angepasst werden: kann der Benutzer Schaltflächen von einer Symbolleiste zu anderen ziehen und Kopieren, Einfügen, Löschen und Bearbeitungsbeschriftungen und Bilder.  Um den Benutzer beim Anpassen der Symbolleiste zu verhindern, können Sie die Symbolleiste auf zwei Arten sperren.  Alle `bLocked` ist das Flag auf `TRUE`, wenn Sie [CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md) aufrufen fest, oder fügt die Befehls\-ID einer einzelnen Schaltfläche der globalen Liste von geschützten Befehlen hinzu, indem die [CMFCToolBarButton::SetProtectedCommands](../Topic/CMFCToolBarButton::SetProtectedCommands.md)\-Methode bei.  
  
 `CMFCToolBarButton` wendet Bilder aus den globalen Auflistungen von Symbolleistenimages in der Anwendung ein.  Diese Auflistungen werden von die Elemente Symbolleiste, [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md) beibehalten.  Weitere Informationen finden Sie unter [CMFCToolBarImages Class](../../mfc/reference/cmfctoolbarimages-class.md).  
  
 Wenn der Benutzer auf eine Schaltfläche klickt, verarbeitet die Elemente Symbolleiste die Mausmeldung und teilt die entsprechende Aktion zur Schaltfläche mit.  Wenn die Schaltfläche eine gültige Befehls\-ID hat, sendet die Elemente Symbolleiste die `WM_COMMAND` Nachricht an den übergeordneten Frames.  
  
 Die `CMFCToolBarButton`\-Klasse ist die Basisklasse für andere Symbolleistenschaltflächenklassen, wie [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md), [CMFCToolBarEditBoxButton Class](../../mfc/reference/cmfctoolbareditboxbutton-class.md) und [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt `CMFCToolBarButton` konfiguriert, indem verschiedene Methoden in der `CMFCToolBarButton`\-Klasse angewendet wird.  Das Beispiel veranschaulicht, wie die Maus und die Tastatureingabe aktiviert, den Bildindex der Schaltfläche festlegen, das umschließende Rechteck der Schaltfläche festlegen, und die Schaltfläche sichtbar.  Dieser Codeausschnitt ist Teil [Tab\-Steuerelement\-Beispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_TabControl#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_TabControl#1)]  
[!CODE [NVC_MFC_TabControl#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_TabControl#2)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## Anforderungen  
 **Header:** afxtoolbarbutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarImages Class](../../mfc/reference/cmfctoolbarimages-class.md)   
 [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)   
 [CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md)