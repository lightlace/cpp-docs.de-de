---
title: "CMFCRibbonBaseElement Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonBaseElement"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonBaseElement class"
ms.assetid: 419ea91b-5062-44cc-b0a3-f87d29566f62
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# CMFCRibbonBaseElement Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCRibbonBaseElement`\-Klasse ist die Basisklasse für alle Elemente, die Sie [Menübandleiste](../../mfc/reference/cmfcribbonbar-class.md) hinzufügen können.  Beispiele für Menübandelementen sind Menübandschaltflächen, Menübandkontrollkästchen und Menübandkombinationsfelder.  
  
## Syntax  
  
```  
class CMFCRibbonBaseElement : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCRibbonBaseElement`|Erstellt ein `CMFCRibbonBaseElement`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonBaseElement::AddToKeyList](../Topic/CMFCRibbonBaseElement::AddToKeyList.md)|Fügt ein keytip für das Menübandelement ein Array keytips hinzu.|  
|[CMFCRibbonBaseElement::AddToListBox](../Topic/CMFCRibbonBaseElement::AddToListBox.md)|Fügt ein Menübandelement dem angegebenen Menübandbefehlslistenfeld hinzu.|  
|[CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar](../Topic/CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar.md)|Gibt an, ob das Menübandelement zur Symbolleiste für den Schnellzugriff hinzugefügt werden kann.|  
|[CMFCRibbonBaseElement::CanBeCompacted](../Topic/CMFCRibbonBaseElement::CanBeCompacted.md)|Gibt an, ob die Größe des Menübandelements kompakt sein kann.|  
|[CMFCRibbonBaseElement::CanBeStretched](../Topic/CMFCRibbonBaseElement::CanBeStretched.md)|Gibt an, ob die Höhe des Menübandelements auf die Höhe einer Menübandzeile vertikal zunehmen kann.|  
|[CMFCRibbonBaseElement::CanBeStretchedHorizontally](../Topic/CMFCRibbonBaseElement::CanBeStretchedHorizontally.md)|Gibt an, ob die Breite des Menübandelements ändern kann.|  
|[CMFCRibbonBaseElement::CleanUpSizes](../Topic/CMFCRibbonBaseElement::CleanUpSizes.md)|Die bereinigt die erlaubt für das Menübandelement auf.|  
|[CMFCRibbonBaseElement::ClosePopupMenu](../Topic/CMFCRibbonBaseElement::ClosePopupMenu.md)|Schließt das Kontextmenü für das Menübandelement.|  
|[CMFCRibbonBaseElement::CopyFrom](../Topic/CMFCRibbonBaseElement::CopyFrom.md)|Kopiert den Zustand angegebenen `CMFCRibbonBaseElement` auf das aktuelle Objekt.|  
|[CMFCRibbonBaseElement::DestroyCtrl](../Topic/CMFCRibbonBaseElement::DestroyCtrl.md)|Zerstört das Menübandelement.|  
|[CMFCRibbonBaseElement::DrawImage](../Topic/CMFCRibbonBaseElement::DrawImage.md)|Zeichnet das Bild für das Menübandelement.|  
|[CMFCRibbonBaseElement::Find](../Topic/CMFCRibbonBaseElement::Find.md)|Gibt den angegebenen Zeiger auf das Menübandelement zurück, wenn das aktuelle Objekt verweist.|  
|[CMFCRibbonBaseElement::FindByData](../Topic/CMFCRibbonBaseElement::FindByData.md)|Ruft einen Zeiger auf das Menübandelement ab, wenn die angegebenen Daten enthält.|  
|[CMFCRibbonBaseElement::FindByID](../Topic/CMFCRibbonBaseElement::FindByID.md)|Ruft einen Zeiger auf das Menübandelement ab, wenn dieses Element durch die angegebene Befehl ID identifiziert wird|  
|[CMFCRibbonBaseElement::FindByOriginal](../Topic/CMFCRibbonBaseElement::FindByOriginal.md)|Ruft einen Zeiger auf das Menübandelement ab, wenn sein Vorlagenmenübandelement das angegebene Menübandelement übereinstimmt.|  
|[CMFCRibbonBaseElement::GetCompactSize](../Topic/CMFCRibbonBaseElement::GetCompactSize.md)|Gibt die komprimierte Größe des Menübandelements zurück.|  
|[CMFCRibbonBaseElement::GetData](../Topic/CMFCRibbonBaseElement::GetData.md)|Ruft die benutzerdefinierten Daten ab, die dem Menübandelement zugeordnet werden.|  
|[CMFCRibbonBaseElement::GetDescription](../Topic/CMFCRibbonBaseElement::GetDescription.md)|Gibt die Beschreibung des Menübandelements zurück.|  
|[CMFCRibbonBaseElement::GetDroppedDown](../Topic/CMFCRibbonBaseElement::GetDroppedDown.md)|Ruft einen Zeiger auf das Menübandelement ab, wenn das Popupmenü unten abgelegt wird.|  
|[CMFCRibbonBaseElement::GetElements](../Topic/CMFCRibbonBaseElement::GetElements.md)|Fügt das aktuelle Menübandelement dem angegebenen Array hinzu.|  
|[CMFCRibbonBaseElement::GetElementsByID](../Topic/CMFCRibbonBaseElement::GetElementsByID.md)|Fügt das aktuelle Menübandelement dem angegebenen Array hinzu, wenn das aktuelle Menübandelement Befehl die angegebene ID enthält|  
|[CMFCRibbonBaseElement::GetHighlighted](../Topic/CMFCRibbonBaseElement::GetHighlighted.md)|Ruft einen Zeiger auf das Menübandelement ab, wenn es hervorgehoben wird.|  
|[CMFCRibbonBaseElement::GetID](../Topic/CMFCRibbonBaseElement::GetID.md)|Gibt die Befehls\-ID des Menübandelements zurück.|  
|[CMFCRibbonBaseElement::GetImageSize](../Topic/CMFCRibbonBaseElement::GetImageSize.md)|Gibt die Größe des Menübandelements zurück.|  
|[CMFCRibbonBaseElement::GetIntermediateSize](../Topic/CMFCRibbonBaseElement::GetIntermediateSize.md)|Gibt die Größe des Menübandelements in seinem zwischen Zustand zurück.|  
|[CMFCRibbonBaseElement::GetKeys](../Topic/CMFCRibbonBaseElement::GetKeys.md)|Gibt das keytip zurück, das mit dem Menübandelement zugeordnet ist.|  
|[CMFCRibbonBaseElement::GetKeyTipRect](../Topic/CMFCRibbonBaseElement::GetKeyTipRect.md)|Ruft das keytip Grenzenrechteck für das Menübandelement ab.|  
|[CMFCRibbonBaseElement::GetKeyTipSize](../Topic/CMFCRibbonBaseElement::GetKeyTipSize.md)|Ruft die Größe des keytip Text.|  
|[CMFCRibbonBaseElement::GetLocationInGroup](../Topic/CMFCRibbonBaseElement::GetLocationInGroup.md)|Gibt den Anzeigenspeicherort des Menübandelements in einer Menübandgruppe an.|  
|[CMFCRibbonBaseElement::GetMenuKeys](../Topic/CMFCRibbonBaseElement::GetMenuKeys.md)|Gibt die keytips zurück, die mit einer Schaltfläche zugeordnet werden.|  
|[CMFCRibbonBaseElement::GetNotifyID](../Topic/CMFCRibbonBaseElement::GetNotifyID.md)|Ruft die Benachrichtigungsbefehls\-id für das Menübandelement ab.|  
|[CMFCRibbonBaseElement::GetOriginal](../Topic/CMFCRibbonBaseElement::GetOriginal.md)|Ruft das ursprüngliche Menübandelement ab.|  
|[CMFCRibbonBaseElement::GetParentCategory](../Topic/CMFCRibbonBaseElement::GetParentCategory.md)|Ruft die Menübandkategorie für das Menübandelement ab.|  
|[CMFCRibbonBaseElement::GetParentPanel](../Topic/CMFCRibbonBaseElement::GetParentPanel.md)|Ruft den Favoritenmenübandbereich ab, der das Menübandelement enthält.|  
|[CMFCRibbonBaseElement::GetParentRibbonBar](../Topic/CMFCRibbonBaseElement::GetParentRibbonBar.md)|Ruft die Elemente Menübandleiste für das Menübandelement ab.|  
|[CMFCRibbonBaseElement::GetParentWnd](../Topic/CMFCRibbonBaseElement::GetParentWnd.md)|Ruft das übergeordnete Fenster für das Menübandelement ab.|  
|[CMFCRibbonBaseElement::GetPressed](../Topic/CMFCRibbonBaseElement::GetPressed.md)|Ruft einen Zeiger auf das Menübandelement ab, wenn der Benutzer es momentan drückt.|  
|[CMFCRibbonBaseElement::GetQuickAccessToolBarID](../Topic/CMFCRibbonBaseElement::GetQuickAccessToolBarID.md)|Ruft die Befehls\-ID des Menübandelements ab, wenn sie in der Symbolleiste für den Schnellzugriff ist.|  
|[CMFCRibbonBaseElement::GetRect](../Topic/CMFCRibbonBaseElement::GetRect.md)|Gibt das umschließende Rechteck des Menübandelements zurück.|  
|[CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md)|Gibt die reguläre Größe des Menübandelements zurück.|  
|[CMFCRibbonBaseElement::GetSize](../Topic/CMFCRibbonBaseElement::GetSize.md)|Gibt die aktuelle Größe des Menübandelements zurück.|  
|[CMFCRibbonBaseElement::GetText](../Topic/CMFCRibbonBaseElement::GetText.md)|Gibt den Text zurück, der mit dem Menübandelement zugeordnet ist.|  
|[CMFCRibbonBaseElement::GetToolTipText](../Topic/CMFCRibbonBaseElement::GetToolTipText.md)|EINGABETASTEquickinfotext des Menübandelements.|  
|[CMFCRibbonBaseElement::GetTopLevelRibbonBar](../Topic/CMFCRibbonBaseElement::GetTopLevelRibbonBar.md)|Ruft die Menübandleiste der obersten Ebene für das Menübandelement ab.|  
|[CMFCRibbonBaseElement::HasCompactMode](../Topic/CMFCRibbonBaseElement::HasCompactMode.md)|Gibt an, ob das Menübandelement einen kompakten Modus hat.|  
|[CMFCRibbonBaseElement::HasFocus](../Topic/CMFCRibbonBaseElement::HasFocus.md)|Gibt an, ob das übergeordnete Element den Tastaturfokus hat.|  
|[CMFCRibbonBaseElement::HasIntermediateMode](../Topic/CMFCRibbonBaseElement::HasIntermediateMode.md)|Gibt an, ob das Menübandelement einen temporären Modus hat.|  
|[CMFCRibbonBaseElement::HasLargeMode](../Topic/CMFCRibbonBaseElement::HasLargeMode.md)|Gibt an, ob das Menübandelement einen großen Modus hat.|  
|[CMFCRibbonBaseElement::HasMenu](../Topic/CMFCRibbonBaseElement::HasMenu.md)|Gibt an, ob das Menübandelement ein Menü enthält.|  
|[CMFCRibbonBaseElement::HitTest](../Topic/CMFCRibbonBaseElement::HitTest.md)|Ruft einen Zeiger auf das Menübandelement ab, wenn der angegebene Punkt in ihm ist.|  
|[CMFCRibbonBaseElement::IsAlignByColumn](../Topic/CMFCRibbonBaseElement::IsAlignByColumn.md)|Gibt an, ob das Menübandelement vertikal mit anderen Menübandelementen ausgerichtet ist.|  
|[CMFCRibbonBaseElement::IsAlwaysLargeImage](../Topic/CMFCRibbonBaseElement::IsAlwaysLargeImage.md)|Gibt an, ob die Menübandelement\-Imagegröße immer groß ist.|  
|[CMFCRibbonBaseElement::IsAutoRepeatMode](../Topic/CMFCRibbonBaseElement::IsAutoRepeatMode.md)|Gibt an, ob das Menübandelement im automatischen Wiederholungsmodus ist.|  
|[CMFCRibbonBaseElement::IsChecked](../Topic/CMFCRibbonBaseElement::IsChecked.md)|Gibt an, ob das Menübandelement überprüft wird.|  
|[CMFCRibbonBaseElement::IsCompactMode](../Topic/CMFCRibbonBaseElement::IsCompactMode.md)|Gibt an, ob das Menübandelement in einem kompakten Modus ist.|  
|[CMFCRibbonBaseElement::IsDefaultMenuLook](../Topic/CMFCRibbonBaseElement::IsDefaultMenuLook.md)||  
|[CMFCRibbonBaseElement::IsDisabled](../Topic/CMFCRibbonBaseElement::IsDisabled.md)|Gibt an, ob das Menübandelement deaktiviert ist.|  
|[CMFCRibbonBaseElement::IsDroppedDown](../Topic/CMFCRibbonBaseElement::IsDroppedDown.md)|Bestimmt, ob das Menübandelement ein Popupmenü angezeigt und unten abgelegt wird.|  
|[CMFCRibbonBaseElement::IsFocused](../Topic/CMFCRibbonBaseElement::IsFocused.md)|Gibt an, ob das Menübandelement den Fokus besitzt.|  
|[CMFCRibbonBaseElement::IsGalleryIcon](../Topic/CMFCRibbonBaseElement::IsGalleryIcon.md)|Gibt an, ob das Menübandelement in einem Menübandkatalog enthalten ist.|  
|[CMFCRibbonBaseElement::IsHighlighted](../Topic/CMFCRibbonBaseElement::IsHighlighted.md)|Gibt an, ob Menübandelement hervorgehoben wird.|  
|[CMFCRibbonBaseElement::IsIntermediateMode](../Topic/CMFCRibbonBaseElement::IsIntermediateMode.md)|Gibt an, ob das aktuelle Bild für das Menübandelement zwischen Größe ist.|  
|[CMFCRibbonBaseElement::IsLargeMode](../Topic/CMFCRibbonBaseElement::IsLargeMode.md)|Gibt an, ob das aktuelle Bild für das Menübandelement großformatig ist.|  
|[CMFCRibbonBaseElement::IsMenuMode](../Topic/CMFCRibbonBaseElement::IsMenuMode.md)|Gibt an, ob das Menübandelement in einem Menü enthalten ist.|  
|[CMFCRibbonBaseElement::IsPressed](../Topic/CMFCRibbonBaseElement::IsPressed.md)|Gibt an, ob der Benutzer auf das Menübandelement geklickt hat.|  
|[CMFCRibbonBaseElement::IsQATMode](../Topic/CMFCRibbonBaseElement::IsQATMode.md)|Gibt an, ob das Menübandelement in der Symbolleiste für den Schnellzugriff enthalten ist.|  
|[CMFCRibbonBaseElement::IsSeparator](../Topic/CMFCRibbonBaseElement::IsSeparator.md)|Gibt an, ob das Menübandelement ein Anzeigentrennzeichen ist.|  
|[CMFCRibbonBaseElement::IsShowGroupBorder](../Topic/CMFCRibbonBaseElement::IsShowGroupBorder.md)|Gibt an, ob das Menübandelement in einer Gruppe enthalten sind, die eine gemeinsame Begrenzung anzeigt.|  
|[CMFCRibbonBaseElement::IsShowTooltipOnBottom](../Topic/CMFCRibbonBaseElement::IsShowTooltipOnBottom.md)|Gibt an, ob die QuickInfo unter dem Menüband angezeigt wird.|  
|[CMFCRibbonBaseElement::IsTabStop](../Topic/CMFCRibbonBaseElement::IsTabStop.md)|Gibt an, ob das Menübandelement mit der Tastatur ausgewählt werden kann.|  
|[CMFCRibbonBaseElement::IsTextAlwaysOnRight](../Topic/CMFCRibbonBaseElement::IsTextAlwaysOnRight.md)|Gibt an, ob der Text für das Menübandelement auf der rechten Seite angezeigt wird.|  
|[CMFCRibbonBaseElement::IsVisible](../Topic/CMFCRibbonBaseElement::IsVisible.md)|Gibt an, ob das Menübandelement gerade angezeigt wird.|  
|[CMFCRibbonBaseElement::IsWholeRowHeight](../Topic/CMFCRibbonBaseElement::IsWholeRowHeight.md)|Gibt an, ob das heigth Anzeige des Menübandelements dasselbe wie die Anzeigenhöhe des Menübandbereichs ist, der es enthält.|  
|[CMFCRibbonBaseElement::NotifyCommand](../Topic/CMFCRibbonBaseElement::NotifyCommand.md)|Sendet eine Befehlsbenachrichtigung zum übergeordneten Fenster des Menübandelements.|  
|[CMFCRibbonBaseElement::NotifyHighlightListItem](../Topic/CMFCRibbonBaseElement::NotifyHighlightListItem.md)|Benachrichtigt das übergeordnete Fenster der Menübandleiste, wenn ein Benutzer ein Menübandelement hervorhebt, das in einer Liste ist.|  
|[CMFCRibbonBaseElement::OnAddToQAToolbar](../Topic/CMFCRibbonBaseElement::OnAddToQAToolbar.md)|Fügt das Menübandelement der angegebenen Symbolleiste für den Schnellzugriff hinzu.|  
|[CMFCRibbonBaseElement::OnAfterChangeRect](../Topic/CMFCRibbonBaseElement::OnAfterChangeRect.md)|Aktualisiert die QuickInfo für das Menübandelement.|  
|[CMFCRibbonBaseElement::OnAutoRepeat](../Topic/CMFCRibbonBaseElement::OnAutoRepeat.md)|Aktualisiert das Menübandelement als Reaktion auf einen längeren Benutzereingaben.|  
|[CMFCRibbonBaseElement::OnCalcTextSize](../Topic/CMFCRibbonBaseElement::OnCalcTextSize.md)|Berechnet die Textgröße für das Menübandelement.|  
|[CMFCRibbonBaseElement::OnChangeMenuHighlight](../Topic/CMFCRibbonBaseElement::OnChangeMenuHighlight.md)|Aufgerufen vom Framework, wenn die Hervorhebung für ein Menübandelement ändern können, das in einem Menü ist.|  
|[CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md)|Aufgerufen durch das Framework, um das Menübandelement zu zeichnen.|  
|[CMFCRibbonBaseElement::OnDrawKeyTip](../Topic/CMFCRibbonBaseElement::OnDrawKeyTip.md)|Aufgerufen vom Framework, um das keytip für das Menübandelement zu zeichnen.|  
|[CMFCRibbonBaseElement::OnDrawMenuImage](../Topic/CMFCRibbonBaseElement::OnDrawMenuImage.md)|Aufgerufen vom Framework, wenn das Menüimage für das Menübandelement gezeichnet wird.|  
|[CMFCRibbonBaseElement::OnDrawOnList](../Topic/CMFCRibbonBaseElement::OnDrawOnList.md)|Aufgerufen durch das Framework, um das Menübandelement in einem Befehlslistenfeld zu zeichnen.|  
|[CMFCRibbonBaseElement::OnKey](../Topic/CMFCRibbonBaseElement::OnKey.md)|Aufgerufen vom Framework, wenn der Benutzer drückt, hat ein keytip und das Menübandelement den Fokus.|  
|[CMFCRibbonBaseElement::OnMenuKey](../Topic/CMFCRibbonBaseElement::OnMenuKey.md)||  
|[CMFCRibbonBaseElement::OnRTLChanged](../Topic/CMFCRibbonBaseElement::OnRTLChanged.md)|Aufgerufen vom Framework, wenn das Layout Richtung ändert.|  
|[CMFCRibbonBaseElement::OnShow](../Topic/CMFCRibbonBaseElement::OnShow.md)|Aufgerufen durch das Framework, um das Menübandelement anzuzeigen oder auszublenden.|  
|[CMFCRibbonBaseElement::OnShowPopupMenu](../Topic/CMFCRibbonBaseElement::OnShowPopupMenu.md)|Aufgerufen vom Framework, wenn das Menübandelement ein Popupmenü angezeigt wird.|  
|[CMFCRibbonBaseElement::PostMenuCommand](../Topic/CMFCRibbonBaseElement::PostMenuCommand.md)||  
|[CMFCRibbonBaseElement::Redraw](../Topic/CMFCRibbonBaseElement::Redraw.md)|Aktualisiert die Anzeige für das Menübandelement.|  
|[CMFCRibbonBaseElement::SetACCData](../Topic/CMFCRibbonBaseElement::SetACCData.md)|Legt die Barrierefreiheitsdaten für das Menübandelement fest.|  
|[CMFCRibbonBaseElement::SetCompactMode](../Topic/CMFCRibbonBaseElement::SetCompactMode.md)|Legt die Anzeigengröße für das Menübandelement fest.|  
|[CMFCRibbonBaseElement::SetData](../Topic/CMFCRibbonBaseElement::SetData.md)|Ordnet ein Datenelement mit dem Menübandelement zu.|  
|[CMFCRibbonBaseElement::SetDefaultMenuLook](../Topic/CMFCRibbonBaseElement::SetDefaultMenuLook.md)||  
|[CMFCRibbonBaseElement::SetDescription](../Topic/CMFCRibbonBaseElement::SetDescription.md)|Legt die Beschreibung für das Menübandelement fest.|  
|[CMFCRibbonBaseElement::SetID](../Topic/CMFCRibbonBaseElement::SetID.md)|Legt die Befehls\-ID des Menübandelements fest.|  
|[CMFCRibbonBaseElement::SetInitialMode](../Topic/CMFCRibbonBaseElement::SetInitialMode.md)|Legt die ursprüngliche Anzeigengröße für das Menübandelement fest.|  
|[CMFCRibbonBaseElement::SetKeys](../Topic/CMFCRibbonBaseElement::SetKeys.md)|Legt ein keytip für das Menübandelement fest.|  
|[CMFCRibbonBaseElement::SetOriginal](../Topic/CMFCRibbonBaseElement::SetOriginal.md)|Legt das ursprüngliche Menübandelement für das Menübandelement fest.|  
|[CMFCRibbonBaseElement::SetParentCategory](../Topic/CMFCRibbonBaseElement::SetParentCategory.md)|Legt die übergeordnete Kategorie für das Menübandelement fest.|  
|[CMFCRibbonBaseElement::SetParentMenu](../Topic/CMFCRibbonBaseElement::SetParentMenu.md)|Legt den Elementen Menücontainer für das Menübandelement fest.|  
|[CMFCRibbonBaseElement::SetParentRibbonBar](../Topic/CMFCRibbonBaseElement::SetParentRibbonBar.md)|Legt die Elemente Menübandleiste für das Menübandelement fest.|  
|[CMFCRibbonBaseElement::SetRect](../Topic/CMFCRibbonBaseElement::SetRect.md)|Legt die Dimensionen fest, fot, das er Rechteck für das Menübandelement anzeigt.|  
|[CMFCRibbonBaseElement::SetText](../Topic/CMFCRibbonBaseElement::SetText.md)|Legt den Text für das Menübandelement fest.|  
|[CMFCRibbonBaseElement::SetTextAlwaysOnRight](../Topic/CMFCRibbonBaseElement::SetTextAlwaysOnRight.md)|Legt den Text fest, damit das Menübandelement auf der rechten Seite anzeigt.|  
|[CMFCRibbonBaseElement::SetToolTipText](../Topic/CMFCRibbonBaseElement::SetToolTipText.md)|Legt den QuickInfo\-Text für das Menübandelement fest.|  
|[CMFCRibbonBaseElement::SetVisible](../Topic/CMFCRibbonBaseElement::SetVisible.md)|Legt den Sichtbarkeitszustand des Menübandelements fest.|  
|[CMFCRibbonBaseElement::StretchHorizontally](../Topic/CMFCRibbonBaseElement::StretchHorizontally.md)|Streckt die Breite des Menübandelements.|  
|[CMFCRibbonBaseElement::StretchToWholeRow](../Topic/CMFCRibbonBaseElement::StretchToWholeRow.md)|Ändert die Anzeigenhöhe des Menübandelements zur angegebenen Zeilenhöhe.|  
|[CMFCRibbonBaseElement::UpdateTooltipInfo](../Topic/CMFCRibbonBaseElement::UpdateTooltipInfo.md)|Aktualisiert den QuickInfo\-Text mithilfe der Befehlsressource für das Menübandelement.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonBaseElement::OnProcessKey](../Topic/CMFCRibbonBaseElement::OnProcessKey.md)|Aufgerufen vom Framework, wenn der Benutzer die Tastenkombination drückt.|  
|[CMFCRibbonBaseElement::OnSetFocus](../Topic/CMFCRibbonBaseElement::OnSetFocus.md)|Aufgerufen vom Framework ausgelöst, wenn ein Menübandelement den Eingabefokus erhält oder verliert.|  
  
## Hinweise  
 Die `CMFCRibbonBaseElement`\-Klasse definiert die Eigenschaften, die allen Menübandelementen gemeinsam sind, die Befehls\-ID, Beschriftung, QuickInfo\-Text, Elementbeschreibung und Zustand enthalten \(der unten gerichtet werden kann, markiert werden, gedrückt werden, deaktiviert sind, überprüft oder abgelegt werden\).  
  
 Die Größe eines Menübandelements wird vom `RibbonImageType`\-Member definiert, der einer der folgenden Werte sein kann:  
  
-   `RibbonImageLarge`  
  
-   `RibbonImageSmall`  
  
 Je nach seiner Größe zeigt ein Menübandelement entweder ein kleines oder großes Bild an.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCRibbonBaseElement` verwendet.  Im Beispiel wird gezeigt, wie ein `CMFCRibbonBaseElement`\-Objekt aus einer Klasse `CMFCRibbonStatusBar`, legen Sie die Beschreibung für das Menübandelement, legen Sie den Text, legen Sie ein keytip und legen den QuickInfo\-Text für das Menübandelement abruft.  Dieser Codeausschnitt ist Teil [Clientbeispiel Videofunktionen](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DrawClient#8](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DrawClient#8)]  
[!CODE [NVC_MFC_DrawClient#9](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DrawClient#9)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
## Anforderungen  
 **Header:** afxbaseribbonelement.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)