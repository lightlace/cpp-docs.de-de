---
title: "CMFCPropertyGridCtrl Class"
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
  - "CMFCPropertyGridCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridCtrl class"
  - "CMFCPropertyGridCtrl::accHitTest method"
  - "CMFCPropertyGridCtrl::accLocation method"
  - "CMFCPropertyGridCtrl::get_accChild method"
  - "CMFCPropertyGridCtrl::get_accDefaultAction method"
  - "CMFCPropertyGridCtrl::get_accDescription method"
  - "CMFCPropertyGridCtrl::get_accName method"
  - "CMFCPropertyGridCtrl::get_accRole method"
  - "CMFCPropertyGridCtrl::get_accState method"
  - "CMFCPropertyGridCtrl::get_accValue method"
  - "CMFCPropertyGridCtrl::PreTranslateMessage method"
ms.assetid: 95877cae-2311-4a2a-9031-0c8c3cf0a5f9
caps.latest.revision: 35
caps.handback.revision: "24"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Unterstützt ein bearbeitbares Eigenschaftenraster, das Eigenschaften in der alphabetischen Reihenfolge oder hierarchische anzeigen kann.  
  
## Syntax  
  
```  
class CMFCPropertyGridCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPropertyGridCtrl::CMFCPropertyGridCtrl](../Topic/CMFCPropertyGridCtrl::CMFCPropertyGridCtrl.md)|Erstellt ein `CMFCPropertyGridCtrl`\-Objekt.|  
|`CMFCPropertyGridCtrl::~CMFCPropertyGridCtrl`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCPropertyGridCtrl::accHitTest`|Aufgerufen vom Framework, um das untergeordnete Element oder das untergeordnete Objekt an einem angegebenen Punkt auf dem Bildschirm abzurufen.  \(Überschreibungen [CWnd::accHitTest](../Topic/CWnd::accHitTest.md).\)|  
|`CMFCPropertyGridCtrl::accLocation`|Aufgerufen durch das Framework, um die angegebenen aktuelle Bildschirmposition des Objekts abzurufen.  \(Überschreibungen [CWnd::accLocation](../Topic/CWnd::accLocation.md).\)|  
|[CMFCPropertyGridCtrl::accSelect](../Topic/CMFCPropertyGridCtrl::accSelect.md)|Aufgerufen durch das Framework, um die Auswahl zu ändern oder den Tastaturfokus des angegebenen Objekts zu verschieben.  \(Überschreibungen [CWnd::accSelect](../Topic/CWnd::accSelect.md).\)|  
|[CMFCPropertyGridCtrl::AddProperty](../Topic/CMFCPropertyGridCtrl::AddProperty.md)|Fügt eine neue Eigenschaft einem Eigenschaftenraster hinzu.|  
|[CMFCPropertyGridCtrl::AlwaysShowUserToolTip](../Topic/CMFCPropertyGridCtrl::AlwaysShowUserToolTip.md)||  
|[CMFCPropertyGridCtrl::CloseColorPopup](../Topic/CMFCPropertyGridCtrl::CloseColorPopup.md)|Schließt das Farben\-Auswahldialogfeld.|  
|[CMFCPropertyGridCtrl::Create](../Topic/CMFCPropertyGridCtrl::Create.md)|Erstellt ein und fügt es dem Eigenschaftenraster Eigenschaftraster\-steuerelement\-Objekt an.|  
|[CMFCPropertyGridCtrl::DeleteProperty](../Topic/CMFCPropertyGridCtrl::DeleteProperty.md)|Löscht die angegebene Eigenschaft aus dem Eigenschaftenraster.|  
|[CMFCPropertyGridCtrl::DrawControlBarColors](../Topic/CMFCPropertyGridCtrl::DrawControlBarColors.md)||  
|[CMFCPropertyGridCtrl::EnableDescriptionArea](../Topic/CMFCPropertyGridCtrl::EnableDescriptionArea.md)|Aktiviert oder deaktiviert den Beschreibungsbereich, der unter der Liste von Eigenschaften angezeigt.|  
|[CMFCPropertyGridCtrl::EnableHeaderCtrl](../Topic/CMFCPropertyGridCtrl::EnableHeaderCtrl.md)|Aktiviert oder deaktiviert das Header\-Steuerelement oben im Eigenschaftraster\-steuerelements.|  
|[CMFCPropertyGridCtrl::EnsureVisible](../Topic/CMFCPropertyGridCtrl::EnsureVisible.md)|Führt ein Eigenschaftenraster Bildlauf durch und erweitert Projekteigenschaftenelemente, bis die angegebene Eigenschaft sichtbar ist.|  
|[CMFCPropertyGridCtrl::ExpandAll](../Topic/CMFCPropertyGridCtrl::ExpandAll.md)|Erweitert oder reduziert alle Eigenschaftraster\-steuerelement\-Knoten.|  
|[CMFCPropertyGridCtrl::FindItemByData](../Topic/CMFCPropertyGridCtrl::FindItemByData.md)|Ruft die Eigenschaft ab, die mit einem benutzerdefinierten `DWORD`\-Wert zugeordnet ist.|  
|`CMFCPropertyGridCtrl::get_accChild`|Aufgerufen durch das Framework, um die Adresse einer `IDispatch`\-Schnittstelle für das angegebene untergeordnete Element abzurufen.  \(Überschreibungen [CWnd::get\_accChild](../Topic/CWnd::get_accChild.md).\)|  
|[CMFCPropertyGridCtrl::get\_accChildCount](../Topic/CMFCPropertyGridCtrl::get_accChildCount.md)|Aufgerufen vom Framework, um die Anzahl der untergeordneten Elemente ab, die diesem Objekt gehören.  \(Überschreibungen [CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md).\)|  
|`CMFCPropertyGridCtrl::get_accDefaultAction`|Aufgerufen durch das Framework, um eine Zeichenfolge abzurufen, die die Standardaktion des Objekts beschreibt.  \(Überschreibungen [CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md).\)|  
|`CMFCPropertyGridCtrl::get_accDescription`|Aufgerufen durch Framework, um eine Zeichenfolge abzurufen, die die visuelle Darstellung des angegebenen Objekts beschreibt.  \(Überschreibungen [CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md).\)|  
|[CMFCPropertyGridCtrl::get\_accFocus](../Topic/CMFCPropertyGridCtrl::get_accFocus.md)|Aufgerufen durch das Framework, um das Objekt ab, das den Tastaturfokus hat.  \(Überschreibungen [CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md).\)|  
|[CMFCPropertyGridCtrl::get\_accHelp](../Topic/CMFCPropertyGridCtrl::get_accHelp.md)|Aufgerufen durch das Framework, um `Help`\-Eigenschaftzeichenfolge eines Objekts abzurufen.  \(Überschreibungen [CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md).\)|  
|[CMFCPropertyGridCtrl::get\_accHelpTopic](../Topic/CMFCPropertyGridCtrl::get_accHelpTopic.md)|Aufgerufen vom Framework, um den vollständigen Pfad der Datei `WinHelp` abzurufen zugeordnet mit dem angegebenen Objekt und dem entsprechenden Bezeichner des Themas in der Datei.  \(Überschreibungen [CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md).\)|  
|[CMFCPropertyGridCtrl::get\_accKeyboardShortcut](../Topic/CMFCPropertyGridCtrl::get_accKeyboardShortcut.md)|Aufgerufen durch das Framework, um des angegebene die Tastenkombination oder Tastenkombinationen Objekts abzurufen.  \(Überschreibungen [CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md).\)|  
|`CMFCPropertyGridCtrl::get_accName`|Aufgerufen vom Framework, um den Namen des angegebenen Objekts abzurufen.  \(Überschreibungen [CWnd::get\_accName](../Topic/CWnd::get_accName.md).\)|  
|`CMFCPropertyGridCtrl::get_accRole`|Aufgerufen vom Framework, um Informationen abzurufen, die die Rolle des angegebenen Objekts beschreibt.  \(Überschreibungen [CWnd::get\_accRole](../Topic/CWnd::get_accRole.md).\)|  
|[CMFCPropertyGridCtrl::get\_accSelection](../Topic/CMFCPropertyGridCtrl::get_accSelection.md)|Aufgerufen vom Framework, um die ausgewählten untergeordneten Elemente aus diesem abzurufenden Objekts.  \(Überschreibungen [CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md).\)|  
|`CMFCPropertyGridCtrl::get_accState`|Aufgerufen vom Framework, um den aktuellen Zustand des angegebenen Objekts abzurufen.  \(Überschreibungen [CWnd::get\_accState](../Topic/CWnd::get_accState.md).\)|  
|`CMFCPropertyGridCtrl::get_accValue`|Aufgerufen vom Framework, um den Wert des angegebenen Objekts abzurufen.  \(Überschreibungen [CWnd::get\_accValue](../Topic/CWnd::get_accValue.md).\)|  
|[CMFCPropertyGridCtrl::GetBkColor](../Topic/CMFCPropertyGridCtrl::GetBkColor.md)|Ruft die Hintergrundfarbe des aktuellen Eigenschaftraster\-steuerelements ab.|  
|[CMFCPropertyGridCtrl::GetBoldFont](../Topic/CMFCPropertyGridCtrl::GetBoldFont.md)|Ruft die Windows\-Schriftart ab, die vom Text im aktuellen im Eigenschaftenraster fett.|  
|[CMFCPropertyGridCtrl::GetCurSel](../Topic/CMFCPropertyGridCtrl::GetCurSel.md)|Ruft die aktuell ausgewählte Eigenschaft ab.|  
|[CMFCPropertyGridCtrl::GetCustomColors](../Topic/CMFCPropertyGridCtrl::GetCustomColors.md)|Ruft die benutzerdefinierten Farben ab, die derzeit für Eigenschaftraster\-steuerelement\-Elemente definiert werden.|  
|[CMFCPropertyGridCtrl::GetDescriptionHeight](../Topic/CMFCPropertyGridCtrl::GetDescriptionHeight.md)|Ruft die Höhe des Beschreibungsbereichs ab, der unten im Eigenschaftenraster gleich ist.|  
|[CMFCPropertyGridCtrl::GetDescriptionRows](../Topic/CMFCPropertyGridCtrl::GetDescriptionRows.md)|Ruft die Anzahl der Zeilen im Beschreibungsbereich des aktuellen Eigenschaftraster\-steuerelements ab.|  
|[CMFCPropertyGridCtrl::GetHeaderCtrl](../Topic/CMFCPropertyGridCtrl::GetHeaderCtrl.md)|Ruft das interne [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)\-Objekt ab, das vom Framework verwendet, um das aktuelle Eigenschaftenraster anzuzeigen.|  
|[CMFCPropertyGridCtrl::GetHeaderHeight](../Topic/CMFCPropertyGridCtrl::GetHeaderHeight.md)|Ruft die Höhe des Eigenschaftraster\-steuerelement\-Headers ab.|  
|[CMFCPropertyGridCtrl::GetLeftColumnWidth](../Topic/CMFCPropertyGridCtrl::GetLeftColumnWidth.md)|Ruft die Breite der linken Spalte des aktuellen Eigenschaftraster\-steuerelements ab, das den Namen der Eigenschaft enthält.|  
|[CMFCPropertyGridCtrl::GetListRect](../Topic/CMFCPropertyGridCtrl::GetListRect.md)|Ruft das umschließende Rechteck des Eigenschaftraster\-steuerelements ab.|  
|[CMFCPropertyGridCtrl::GetProperty](../Topic/CMFCPropertyGridCtrl::GetProperty.md)|Ruft einen Zeiger auf das Eigenschaftenobjekt ab, die dem angegebenen Index eines Eigenschaftenraster\-Steuerelements entspricht.|  
|[CMFCPropertyGridCtrl::GetPropertyColumnWidth](../Topic/CMFCPropertyGridCtrl::GetPropertyColumnWidth.md)|Ruft die aktuelle Breite der Spalte ab, die Eigenschaftswerte enthält.|  
|[CMFCPropertyGridCtrl::GetPropertyCount](../Topic/CMFCPropertyGridCtrl::GetPropertyCount.md)|Ruft die Anzahl von Eigenschaften in einem Eigenschaftenraster ab.|  
|[CMFCPropertyGridCtrl::GetRowHeight](../Topic/CMFCPropertyGridCtrl::GetRowHeight.md)|Ruft die Höhe einer Zeile im Eigenschaftenraster ab.|  
|[CMFCPropertyGridCtrl::GetScrollBarCtrl](../Topic/CMFCPropertyGridCtrl::GetScrollBarCtrl.md)|Ruft einen Zeiger auf das ScrollBar\-Steuerelement im Eigenschaftenraster ab.  \(Überschreibungen [CWnd::GetScrollBarCtrl](../Topic/CWnd::GetScrollBarCtrl.md).\)|  
|[CMFCPropertyGridCtrl::GetTextColor](../Topic/CMFCPropertyGridCtrl::GetTextColor.md)|Ruft die Farbe des Texts der Projekteigenschaftenelemente im aktuellen Eigenschaftenraster ab.|  
|`CMFCPropertyGridCtrl::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCPropertyGridCtrl::HitTest](../Topic/CMFCPropertyGridCtrl::HitTest.md)|Ruft einen Zeiger auf das Eigenschaftenobjekt ab, das einem Eigenschaftenraster\-Steuerelement entspricht, wenn ein bestimmter Punkt im Element ist.  Diese Methode gibt auch den Bereich im Eigenschaftenraster an, das den Punkt enthält.|  
|[CMFCPropertyGridCtrl::InitHeader](../Topic/CMFCPropertyGridCtrl::InitHeader.md)|Initialisiert das interne [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)\-Objekt, dem das Framework verwendet, um das aktuelle Eigenschaftenraster anzuzeigen.|  
|[CMFCPropertyGridCtrl::IsAlphabeticMode](../Topic/CMFCPropertyGridCtrl::IsAlphabeticMode.md)|Gibt an, ob ein Eigenschaftenraster im alphabetischen Modus ist.|  
|[CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip](../Topic/CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip.md)||  
|[CMFCPropertyGridCtrl::IsDescriptionArea](../Topic/CMFCPropertyGridCtrl::IsDescriptionArea.md)|Gibt an, ob der Beschreibungsbereich des Eigenschaftraster\-steuerelements angezeigt wird.|  
|[CMFCPropertyGridCtrl::IsGroupNameFullWidth](../Topic/CMFCPropertyGridCtrl::IsGroupNameFullWidth.md)|Gibt an, ob jeder Eigenschaftengruppenname über die Breite des aktuellen Eigenschaftraster\-steuerelements angezeigt wird.|  
|[CMFCPropertyGridCtrl::IsHeaderCtrl](../Topic/CMFCPropertyGridCtrl::IsHeaderCtrl.md)|Gibt an, ob das Header\-Steuerelement angezeigt wird.|  
|[CMFCPropertyGridCtrl::IsMarkModifiedProperties](../Topic/CMFCPropertyGridCtrl::IsMarkModifiedProperties.md)|Gibt an, wie das Eigenschaftenraster geänderte Eigenschaften angezeigt.|  
|[CMFCPropertyGridCtrl::IsShowDragContext](../Topic/CMFCPropertyGridCtrl::IsShowDragContext.md)|Gibt an, ob das Framework die Namens\- und Wertsspalten des aktuellen Eigenschaftraster\-steuerelements neu gezeichnet wird, wenn ein Benutzer die Größe der Spalten ändert.|  
|[CMFCPropertyGridCtrl::IsVSDotNetLook](../Topic/CMFCPropertyGridCtrl::IsVSDotNetLook.md)|Gibt an, ob die Darstellung des Eigenschaftraster\-steuerelements im Format ist, das von .NET VS verwendet wird.|  
|[CMFCPropertyGridCtrl::MarkModifiedProperties](../Topic/CMFCPropertyGridCtrl::MarkModifiedProperties.md)|Gibt an, wie geänderte Eigenschaften angezeigt.|  
|`CMFCPropertyGridCtrl::PreTranslateMessage`|Wird von Klasse [CWinApp](../../mfc/reference/cwinapp-class.md), um Fenstermeldungen zu übersetzen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  \(Überschreibungen [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCPropertyGridCtrl::RemoveAll](../Topic/CMFCPropertyGridCtrl::RemoveAll.md)|Entfernt alle Eigenschaftobjekte von einem Eigenschaftenraster.|  
|[CMFCPropertyGridCtrl::ResetOriginalValues](../Topic/CMFCPropertyGridCtrl::ResetOriginalValues.md)|Stellt den ursprünglichen Wert aller Eigenschaften wiederher.|  
|[CMFCPropertyGridCtrl::SetAlphabeticMode](../Topic/CMFCPropertyGridCtrl::SetAlphabeticMode.md)|Setzt oder alphabetischer Modus der zurückgesetzt.|  
|[CMFCPropertyGridCtrl::SetBoolLabels](../Topic/CMFCPropertyGridCtrl::SetBoolLabels.md)|Gibt den Text von booleschen Bezeichnungen.|  
|[CMFCPropertyGridCtrl::SetCurSel](../Topic/CMFCPropertyGridCtrl::SetCurSel.md)|Wählt eine Eigenschaft in einem Eigenschaftenraster aus.|  
|[CMFCPropertyGridCtrl::SetCustomColors](../Topic/CMFCPropertyGridCtrl::SetCustomColors.md)|Gibt benutzerdefinierte Farben für verschiedene Eigenschaftraster\-steuerelement\-Elemente an.|  
|[CMFCPropertyGridCtrl::SetDescriptionRows](../Topic/CMFCPropertyGridCtrl::SetDescriptionRows.md)|Gibt die Anzahl der Zeilen an, die im Beschreibungsabschnitt des aktuellen Eigenschaftraster\-steuerelements anzuzeigen.|  
|[CMFCPropertyGridCtrl::SetGroupNameFullWidth](../Topic/CMFCPropertyGridCtrl::SetGroupNameFullWidth.md)|Gibt an, ob die gesamte Breite des Kategoriennamens für eine Gruppe von Eigenschaften im aktuellen Eigenschaftenraster anzeigt.|  
|[CMFCPropertyGridCtrl::SetListDelimiter](../Topic/CMFCPropertyGridCtrl::SetListDelimiter.md)|Definiert ein Zeichen, das als Trennzeichen in einer Liste von Eigenschaftswerten verwendet wird.|  
|[CMFCPropertyGridCtrl::SetShowDragContext](../Topic/CMFCPropertyGridCtrl::SetShowDragContext.md)|Gibt an, ob das Framework die Namens\- und Wertsspalten des aktuellen Eigenschaftraster\-steuerelements neu gezeichnet wird, wenn ein Benutzer die Größe der Spalten ändert.|  
|[CMFCPropertyGridCtrl::SetVSDotNetLook](../Topic/CMFCPropertyGridCtrl::SetVSDotNetLook.md)|Legt die Darstellung des Eigenschaftraster\-steuerelements dem Stil fest, das in VS .NET verwendet wird.|  
|[CMFCPropertyGridCtrl::UpdateColor](../Topic/CMFCPropertyGridCtrl::UpdateColor.md)|Legt den Farbwert der aktuell ausgewählten Farbeigenschaft fest.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPropertyGridCtrl::AdjustLayout](../Topic/CMFCPropertyGridCtrl::AdjustLayout.md)|Aktualisiert das Eigenschaftenraster und seine Eigenschaften neu.|  
|[CMFCPropertyGridCtrl::CompareProps](../Topic/CMFCPropertyGridCtrl::CompareProps.md)|Aufgerufen durch das Eigenschaftenraster, um Eigenschaften zu sortieren.|  
|[CMFCPropertyGridCtrl::EditItem](../Topic/CMFCPropertyGridCtrl::EditItem.md)|Aufgerufen vom Framework wenn der Benutzer beginnt, per eine Eigenschaft zu ändern.|  
|[CMFCPropertyGridCtrl::EndEditItem](../Topic/CMFCPropertyGridCtrl::EndEditItem.md)|Aufgerufen vom Framework, wenn der Benutzer angehalten wird, eine Eigenschaft zu ändern.|  
|[CMFCPropertyGridCtrl::Init](../Topic/CMFCPropertyGridCtrl::Init.md)|Aufgerufen vom Framework, um ein Eigenschaftenraster zu initialisieren.|  
|[CMFCPropertyGridCtrl::OnChangeSelection](../Topic/CMFCPropertyGridCtrl::OnChangeSelection.md)|Aufgerufen vom Framework, wenn die aktuelle Auswahl geändert wird.|  
|[CMFCPropertyGridCtrl::OnClickButton](../Topic/CMFCPropertyGridCtrl::OnClickButton.md)|Aufgerufen vom Framework, wenn auf eine Eigenschaftschaltfläche geklickt wird.|  
|[CMFCPropertyGridCtrl::OnDrawBorder](../Topic/CMFCPropertyGridCtrl::OnDrawBorder.md)|Aufgerufen durch das Framework, um einen Rahmen um ein Eigenschaftenraster zu zeichnen.|  
|[CMFCPropertyGridCtrl::OnDrawDescription](../Topic/CMFCPropertyGridCtrl::OnDrawDescription.md)|Aufgerufen vom Framework, um den Beschreibungsbereich zu zeichnen und den Beschreibungstext anzuzeigen.|  
|[CMFCPropertyGridCtrl::OnDrawList](../Topic/CMFCPropertyGridCtrl::OnDrawList.md)|Aufgerufen vom Framework, um die Liste der Eigenschaften im Eigenschaftenraster anzuzeigen.|  
|[CMFCPropertyGridCtrl::OnDrawProperty](../Topic/CMFCPropertyGridCtrl::OnDrawProperty.md)|Aufgerufen vom Framework, um eine Eigenschaft anzuzeigen.|  
|[CMFCPropertyGridCtrl::OnPropertyChanged](../Topic/CMFCPropertyGridCtrl::OnPropertyChanged.md)|Aufgerufen vom Framework, wenn der Wert einer Eigenschaft geändert wird.|  
|[CMFCPropertyGridCtrl::OnSelectCombo](../Topic/CMFCPropertyGridCtrl::OnSelectCombo.md)|Aufgerufen vom Framework, wenn eine Eigenschaft, die ein Kombinationsfeld\-Steuerelement enthält, ausgewählt ist.|  
|[CMFCPropertyGridCtrl::ValidateItemData](../Topic/CMFCPropertyGridCtrl::ValidateItemData.md)|Aufgerufen durch das Framework, um Eigenschaftendaten zu überprüfen.|  
  
## Hinweise  
 Die Klasse erfasst `CMFCPropertyGridCtrl` ein Eigenschaftenraster, das die bearbeitbaren Eigenschaften enthält, die von der [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)\-Klasse abgeleitet werden.  Jede Eigenschaft kann einen Typ darstellen und kann Unterelemente enthalten.  Das Eigenschaftenraster unterstützt einen in der Größe veränderbaren Bereich unten, der die Beschreibung einer ausgewählten Eigenschaft anzeigen kann.  
  
 Um ein Eigenschaftenraster zu verwenden, erstellen Sie ein `CMFCPropertyGridCtrl`\-Objekt und rufen dann die [CMFCPropertyGridCtrl::Create](../Topic/CMFCPropertyGridCtrl::Create.md)\-Methode auf.  Verwenden Sie die [CMFCPropertyGridCtrl::AddProperty](../Topic/CMFCPropertyGridCtrl::AddProperty.md)\-Methode, um Eigenschaften der Liste hinzuzufügen.  
  
## Auswahl\-Eigenschaften  
 Anstatt, einen Wert anzugeben, kann ein Eigenschaftenelement ein Dialogfeld starten, das dem Benutzer ermöglicht, eine Farbe, eine Datei oder eine Schriftart auswählen.  
  
 Die folgende Tabelle zeigt vier Auswahleigenschaftentypen auf:  
  
|Klasse|Description|  
|------------|-----------------|  
|[CMFCPropertyGridProperty Class](../../mfc/reference/cmfcpropertygridproperty-class.md)|Eine allgemeine Eigenschaft, die verwendet wird, um den Wert von Zeichenfolgen, boolesche Werte, Datumsangaben usw. anzugeben.|  
|[CMFCPropertyGridColorProperty Class](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)|Eine Eigenschaft, die verwendet wird, um einen Farbwert auszuwählen.|  
|[CMFCPropertyGridFileProperty Class](../../mfc/reference/cmfcpropertygridfileproperty-class.md)|Eine Eigenschaft, die verwendet wird, um eine Datei auszuwählen.|  
|[CMFCPropertyGridFontProperty Class](../../mfc/reference/cmfcpropertygridfontproperty-class.md)|Eine Eigenschaft, die verwendet wird, um eine Schriftart auswählen.|  
  
## Abbildungen  
 Die folgenden Abbildungen bieten ein Eigenschaftenraster dar, das Eigenschaften auf zwei Arten anzeigt.  Die erste Figur werden Eigenschaften hierarchisch an und die zweite werden Eigenschaften alphabetisch an.  
  
 ![PropertySheet&#45;Eigenschaftenliste](../../mfc/reference/media/proplist.png "PropList")  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Eigenschaftraster\-steuerelement\-Objekt konfiguriert, indem verschiedene Methoden in der `CMFCPropertyGridCtrl`\-Klasse angewendet wird.  Das Beispiel zeigt, wie das Header\-Steuerelement aktiviert, aktiviert der Beschreibungsbereich und für die Darstellung des Eigenschaftraster\-steuerelements fest.  Das Beispiel zeigt auch, wie der alphabetischen Modus für das Steuerelement, wobei das Steuerelement alle Eigenschaften sortiert, die es durch den Eigenschaftennamen enthält festgelegt wird und wie die benutzerdefinierte Farben für verschiedene Elemente des Eigenschaftraster\-steuerelements festgelegt wird.  Dieses Beispiel ist Teil [Neue Kontrollprobe](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#14](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#14)]  
[!CODE [NVC_MFC_NewControls#16](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#16)]  
[!CODE [NVC_MFC_NewControls#20](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#20)]  
[!CODE [NVC_MFC_NewControls#21](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#21)]  
[!CODE [NVC_MFC_NewControls#24](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#24)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)  
  
## Anforderungen  
 **Header:** afxpropertygridctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)