---
title: "CMFCPropertyGridProperty Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertyGridProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridProperty class"
ms.assetid: 36f3fabe-0efe-468b-8a0b-5a7956db38a2
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCPropertyGridProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Objekt `CMFCPropertyGridProperty` stellt ein Listenelement in einem Eigenschaftenlistensteuerelement dar.  
  
## Syntax  
  
```  
class CMFCPropertyGridProperty : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPropertyGridProperty::CMFCPropertyGridProperty](../Topic/CMFCPropertyGridProperty::CMFCPropertyGridProperty.md)|Erstellt ein `CMFCPropertyGridProperty`\-Objekt.|  
|`CMFCPropertyGridProperty::~CMFCPropertyGridProperty`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPropertyGridProperty::AddOption](../Topic/CMFCPropertyGridProperty::AddOption.md)|Fügt ein neues Listenelement einem Eigenschaftenlistensteuerelement hinzu.|  
|[CMFCPropertyGridProperty::AddSubItem](../Topic/CMFCPropertyGridProperty::AddSubItem.md)|Fügt ein untergeordnetes Element einer Eigenschaft hinzu.|  
|[CMFCPropertyGridProperty::AdjustButtonRect](../Topic/CMFCPropertyGridProperty::AdjustButtonRect.md)|Aufgerufen vom übergeordneten Eigenschaftenlistensteuerelement, um eine Eigenschaft mitzuteilen, um das umschließende Rechteck eines eingebetteten Schaltfläche Größe zu ändern.|  
|[CMFCPropertyGridProperty::AdjustInPlaceEditRect](../Topic/CMFCPropertyGridProperty::AdjustInPlaceEditRect.md)|Ruft die Grenzen des Textfelds und des optionalen Drehfelds ab, die verwendet werden, um einen Eigenschaftswert festzulegen.|  
|[CMFCPropertyGridProperty::AllowEdit](../Topic/CMFCPropertyGridProperty::AllowEdit.md)|Führt eine Eigenschaft entweder bearbeitbar oder schreibgeschützt.|  
|[CMFCPropertyGridProperty::CreateInPlaceEdit](../Topic/CMFCPropertyGridProperty::CreateInPlaceEdit.md)|Aufgerufen durch das Framework, um ein bearbeitbares Steuerelement für eine Eigenschaft zu erstellen.|  
|[CMFCPropertyGridProperty::CreateSpinControl](../Topic/CMFCPropertyGridProperty::CreateSpinControl.md)|Aufgerufen durch das Framework, um ein bearbeitbares Spinner\-Steuerelement zu erstellen.|  
|[CMFCPropertyGridProperty::Enable](../Topic/CMFCPropertyGridProperty::Enable.md)|Aktiviert oder deaktiviert eine Eigenschaft.|  
|[CMFCPropertyGridProperty::EnableSpinControl](../Topic/CMFCPropertyGridProperty::EnableSpinControl.md)|Aktiviert oder deaktiviert ein Drehfeldsteuerelement, das verwendet wird, um einen Eigenschaftswert zu ändern.|  
|[CMFCPropertyGridProperty::Expand](../Topic/CMFCPropertyGridProperty::Expand.md)|Erweitert oder reduziert, eine Eigenschaft mit untergeordneten Eigenschaften enthält.|  
|[CMFCPropertyGridProperty::FormatProperty](../Topic/CMFCPropertyGridProperty::FormatProperty.md)|Formatiert die Textdarstellung eines Eigenschaftswerts.|  
|[CMFCPropertyGridProperty::GetData](../Topic/CMFCPropertyGridProperty::GetData.md)|Ruft einen Wert ab, der `DWORD` mit einer Eigenschaft zugeordnet ist.|  
|[CMFCPropertyGridProperty::GetDescription](../Topic/CMFCPropertyGridProperty::GetDescription.md)|Ruft eine Eigenschaftenbeschreibung ab.|  
|[CMFCPropertyGridProperty::GetExpandedSubItems](../Topic/CMFCPropertyGridProperty::GetExpandedSubItems.md)|Ruft die Anzahl der erweiterten Unterelementen ab.|  
|[CMFCPropertyGridProperty::GetHierarchyLevel](../Topic/CMFCPropertyGridProperty::GetHierarchyLevel.md)|Ruft den nullbasierten Index der Hierarchienebene der Eigenschaft ab.|  
|[CMFCPropertyGridProperty::GetName](../Topic/CMFCPropertyGridProperty::GetName.md)|Ruft den Namen der Eigenschaft ab.|  
|[CMFCPropertyGridProperty::GetNameTooltip](../Topic/CMFCPropertyGridProperty::GetNameTooltip.md)|Aufgerufen vom Framework, um den Namen der Eigenschaft in einer QuickInfo anzuzeigen.|  
|[CMFCPropertyGridProperty::GetOption](../Topic/CMFCPropertyGridProperty::GetOption.md)|Ruft den Text der Option ab, die über einen Index angegeben wird.|  
|[CMFCPropertyGridProperty::GetOptionCount](../Topic/CMFCPropertyGridProperty::GetOptionCount.md)|Ruft die Anzahl der Optionen ab, die einer Eigenschaft gehören.|  
|[CMFCPropertyGridProperty::GetOriginalValue](../Topic/CMFCPropertyGridProperty::GetOriginalValue.md)|Ruft den Anfangswert der aktuellen \- Eigenschaft ab.|  
|[CMFCPropertyGridProperty::GetParent](../Topic/CMFCPropertyGridProperty::GetParent.md)|Ruft einen Zeiger auf eine übergeordnete Eigenschaft ab.|  
|[CMFCPropertyGridProperty::GetRect](../Topic/CMFCPropertyGridProperty::GetRect.md)|Ruft das umschließende Rechteck einer Eigenschaft ab.|  
|[CMFCPropertyGridProperty::GetSubItem](../Topic/CMFCPropertyGridProperty::GetSubItem.md)|Ruft eine untergeordnete Eigenschaft ab, die durch einen nullbasierten Index identifiziert wird.|  
|[CMFCPropertyGridProperty::GetSubItemsCount](../Topic/CMFCPropertyGridProperty::GetSubItemsCount.md)|Ruft die Anzahl der Unterelementen ab.|  
|`CMFCPropertyGridProperty::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCPropertyGridProperty::GetValue](../Topic/CMFCPropertyGridProperty::GetValue.md)|Ruft einen Eigenschaftswert ab.|  
|[CMFCPropertyGridProperty::GetValueTooltip](../Topic/CMFCPropertyGridProperty::GetValueTooltip.md)|Aufgerufen vom Framework, um die Textdarstellung des Eigenschaftswerts abzurufen, der dann in einer QuickInfo angezeigt wird.|  
|[CMFCPropertyGridProperty::HitTest](../Topic/CMFCPropertyGridProperty::HitTest.md)|Zeigt auf die \- Eigenschaft ein Objekt, die zum Eigenschaftenlistenelement entspricht, das einem Punkt entspricht.|  
|[CMFCPropertyGridProperty::IsAllowEdit](../Topic/CMFCPropertyGridProperty::IsAllowEdit.md)|Gibt an, ob eine Eigenschaft bearbeitet werden kann.|  
|[CMFCPropertyGridProperty::IsEnabled](../Topic/CMFCPropertyGridProperty::IsEnabled.md)|Gibt an, ob eine Eigenschaft aktiviert oder deaktiviert wird.|  
|[CMFCPropertyGridProperty::IsExpanded](../Topic/CMFCPropertyGridProperty::IsExpanded.md)|Gibt an, ob eine Eigenschaft erweitert oder reduziert wird.|  
|[CMFCPropertyGridProperty::IsGroup](../Topic/CMFCPropertyGridProperty::IsGroup.md)|Gibt an, ob die aktuelle Eigenschaft eine Gruppe darstellt.|  
|[CMFCPropertyGridProperty::IsInPlaceEditing](../Topic/CMFCPropertyGridProperty::IsInPlaceEditing.md)|Gibt an, ob die aktuelle Eigenschaft bearbeitet werden kann.|  
|[CMFCPropertyGridProperty::IsModified](../Topic/CMFCPropertyGridProperty::IsModified.md)|Gibt an, ob die aktuelle Eigenschaft geändert wird.|  
|[CMFCPropertyGridProperty::IsParentExpanded](../Topic/CMFCPropertyGridProperty::IsParentExpanded.md)|Gibt an, ob die übergeordneten Elemente der aktuellen \- Eigenschaft erweitert werden.|  
|[CMFCPropertyGridProperty::IsSelected](../Topic/CMFCPropertyGridProperty::IsSelected.md)|Gibt an, ob die aktuelle Eigenschaft ausgewählt wird.|  
|[CMFCPropertyGridProperty::IsVisible](../Topic/CMFCPropertyGridProperty::IsVisible.md)|Gibt an, ob die aktuelle Eigenschaft sichtbar ist.|  
|[CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md)|Aufgerufen vom Framework, wenn der Benutzer auf eine Schaltfläche klickt, die in einer Eigenschaft enthalten ist.|  
|[CMFCPropertyGridProperty::OnClickName](../Topic/CMFCPropertyGridProperty::OnClickName.md)|Aufgerufen durch ein übergeordnetes Eigenschaftenlistensteuerelement, wenn ein Benutzer in das Namensfeld einer Eigenschaft klicken.|  
|[CMFCPropertyGridProperty::OnClickValue](../Topic/CMFCPropertyGridProperty::OnClickValue.md)|Aufgerufen durch ein übergeordnetes Eigenschaftenlistensteuerelement, wenn ein Benutzer auf das Wertsfeld einer Eigenschaft klicken.|  
|[CMFCPropertyGridProperty::OnCloseCombo](../Topic/CMFCPropertyGridProperty::OnCloseCombo.md)|Aufgerufen vom Framework ausgelöst, wenn ein Kombinationsfeld, das in einer Eigenschaft enthalten ist, geschlossen wird.|  
|[CMFCPropertyGridProperty::OnDblClk](../Topic/CMFCPropertyGridProperty::OnDblClk.md)|Aufgerufen vom Framework, wenn der Benutzer auf eine Eigenschaft doppelklickt.|  
|[CMFCPropertyGridProperty::OnDrawButton](../Topic/CMFCPropertyGridProperty::OnDrawButton.md)|Aufgerufen vom Framework, um eine Schaltfläche zu zeichnen, die in einer Eigenschaft enthalten ist.|  
|[CMFCPropertyGridProperty::OnDrawDescription](../Topic/CMFCPropertyGridProperty::OnDrawDescription.md)|Aufgerufen vom Framework, um die Eigenschaftenbeschreibung anzuzeigen.|  
|[CMFCPropertyGridProperty::OnDrawExpandBox](../Topic/CMFCPropertyGridProperty::OnDrawExpandBox.md)|Aufgerufen vom Framework, um ein erweiternsfeldsteuerelement neben einer Eigenschaft zu zeichnen, die untergeordnete Eigenschaften enthält.|  
|[CMFCPropertyGridProperty::OnDrawName](../Topic/CMFCPropertyGridProperty::OnDrawName.md)|Aufgerufen durch das Framework, um den Eigenschaftennamen anzuzeigen.|  
|[CMFCPropertyGridProperty::OnDrawValue](../Topic/CMFCPropertyGridProperty::OnDrawValue.md)|Aufgerufen vom Framework, um den Eigenschaftswert anzuzeigen.|  
|[CMFCPropertyGridProperty::OnEdit](../Topic/CMFCPropertyGridProperty::OnEdit.md)|Aufgerufen vom Framework, wenn der Benutzer im Begriff ist, einen Eigenschaftswert zu ändern.|  
|[CMFCPropertyGridProperty::OnEndEdit](../Topic/CMFCPropertyGridProperty::OnEndEdit.md)|Aufgerufen vom Framework, wenn der Benutzer einen Eigenschaftswert Ändern beendet wird.|  
|[CMFCPropertyGridProperty::OnKillSelection](../Topic/CMFCPropertyGridProperty::OnKillSelection.md)||  
|[CMFCPropertyGridProperty::OnPosSizeChanged](../Topic/CMFCPropertyGridProperty::OnPosSizeChanged.md)||  
|[CMFCPropertyGridProperty::OnRClickName](../Topic/CMFCPropertyGridProperty::OnRClickName.md)|Aufgerufen vom Framework, wenn der Benutzer mit der rechten Maustaste in Eigenschaftennamenbereich klickt.|  
|[CMFCPropertyGridProperty::OnRClickValue](../Topic/CMFCPropertyGridProperty::OnRClickValue.md)|Aufgerufen vom Framework, wenn der Benutzer mit der rechten Maustaste in Eigenschaftswertbereich klickt.|  
|[CMFCPropertyGridProperty::OnSelectCombo](../Topic/CMFCPropertyGridProperty::OnSelectCombo.md)|Aufgerufen vom Framework, wenn der Benutzer ein Element aus dem bearbeitbaren Kombinationsfeld auswählt.|  
|[CMFCPropertyGridProperty::OnSetCursor](../Topic/CMFCPropertyGridProperty::OnSetCursor.md)|Aufgerufen vom Framework, wenn der Mauszeiger auf ein Eigenschaftenelement bewegt.|  
|[CMFCPropertyGridProperty::OnSetSelection](../Topic/CMFCPropertyGridProperty::OnSetSelection.md)||  
|[CMFCPropertyGridProperty::OnUpdateValue](../Topic/CMFCPropertyGridProperty::OnUpdateValue.md)|Aufgerufen vom Framework, wenn der Wert einer bearbeitbaren \- Eigenschaft geändert hat.|  
|[CMFCPropertyGridProperty::PushChar](../Topic/CMFCPropertyGridProperty::PushChar.md)|Aufgerufen vom Eigenschaftenlistensteuerelement, wenn die Eigenschaft aktiviert ist und vom Benutzer gibt ein neues Zeichen ein.|  
|[CMFCPropertyGridProperty::Redraw](../Topic/CMFCPropertyGridProperty::Redraw.md)|Aktualisiert die Eigenschaft neu.|  
|[CMFCPropertyGridProperty::RemoveAllOptions](../Topic/CMFCPropertyGridProperty::RemoveAllOptions.md)|Entfernt alle Optionen \(\- Elemente\) aus einer Eigenschaft.|  
|[CMFCPropertyGridProperty::RemoveSubItem](../Topic/CMFCPropertyGridProperty::RemoveSubItem.md)|Entfernt das angegebene Unterelement.|  
|[CMFCPropertyGridProperty::ResetOriginalValue](../Topic/CMFCPropertyGridProperty::ResetOriginalValue.md)|Stellt den ursprünglichen Wert einer geänderten Eigenschaft wieder her.|  
|[CMFCPropertyGridProperty::SetData](../Topic/CMFCPropertyGridProperty::SetData.md)|Ordnet einen `DWORD`\-Wert mit einer Eigenschaft zu.|  
|[CMFCPropertyGridProperty::SetDescription](../Topic/CMFCPropertyGridProperty::SetDescription.md)|Gibt den Text an, der die aktuelle Eigenschaft beschreibt.|  
|[CMFCPropertyGridProperty::SetName](../Topic/CMFCPropertyGridProperty::SetName.md)|Legt den Namen einer Eigenschaft.|  
|[CMFCPropertyGridProperty::SetOriginalValue](../Topic/CMFCPropertyGridProperty::SetOriginalValue.md)|Legt den ursprünglichen Wert einer bearbeitbaren Eigenschaft fest.|  
|[CMFCPropertyGridProperty::SetValue](../Topic/CMFCPropertyGridProperty::SetValue.md)|Legt den Wert einer Eigenschaftrastereigenschaft fest.|  
|[CMFCPropertyGridProperty::Show](../Topic/CMFCPropertyGridProperty::Show.md)|In oder aus einer Eigenschaft.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPropertyGridProperty::CreateCombo](../Topic/CMFCPropertyGridProperty::CreateCombo.md)|Aufgerufen vom Framework, um ein Kombinationsfeld einer Eigenschaft hinzuzufügen.|  
|[CMFCPropertyGridProperty::HasButton](../Topic/CMFCPropertyGridProperty::HasButton.md)|Gibt an, ob eine Eigenschaft eine Schaltfläche enthält.|  
|[CMFCPropertyGridProperty::Init](../Topic/CMFCPropertyGridProperty::Init.md)|Aufgerufen vom Framework, um ein Eigenschaftenobjekt zu initialisieren.|  
|[CMFCPropertyGridProperty::IsSubItem](../Topic/CMFCPropertyGridProperty::IsSubItem.md)|Gibt an, ob die angegebene Eigenschaft ein Unterelement der aktuellen \- Eigenschaft ist.|  
|[CMFCPropertyGridProperty::IsValueChanged](../Topic/CMFCPropertyGridProperty::IsValueChanged.md)|Gibt an, ob der Wert der aktuellen Eigenschaft geändert wurde.|  
|[CMFCPropertyGridProperty::OnCtlColor](../Topic/CMFCPropertyGridProperty::OnCtlColor.md)|Aufgerufen vom Framework, wenn ein Pinsel abrufen muss, um die Hintergrundfarbe einer Eigenschaft auszufüllen.|  
|[CMFCPropertyGridProperty::OnDestroyWindow](../Topic/CMFCPropertyGridProperty::OnDestroyWindow.md)|Aufgerufen vom Framework, wenn eine Eigenschaft zerstört wird, oder wenn bearbeiten, wird beendet.|  
|[CMFCPropertyGridProperty::OnKillFocus](../Topic/CMFCPropertyGridProperty::OnKillFocus.md)|Aufgerufen vom Framework, wenn die Eigenschaft den Eingabefokus verliert.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPropertyGridProperty::m\_strFormatDouble](../Topic/CMFCPropertyGridProperty::m_strFormatDouble.md)|Formatzeichenfolge für einen Wert des Typdoubles.|  
|[CMFCPropertyGridProperty::m\_strFormatFloat](../Topic/CMFCPropertyGridProperty::m_strFormatFloat.md)|Formatzeichenfolge für einen Wert vom Typ float.|  
|[CMFCPropertyGridProperty::m\_strFormatLong](../Topic/CMFCPropertyGridProperty::m_strFormatLong.md)|Formatzeichenfolge für einen Wert des Typs lang.|  
|[CMFCPropertyGridProperty::m\_strFormatShort](../Topic/CMFCPropertyGridProperty::m_strFormatShort.md)|Formatzeichenfolge für einen Wert des Typs kurz.|  
  
## Hinweise  
 Verwenden Sie ein `CMFCPropertyGridProperty`\-Objekt, um eine Eigenschaft darstellt, die Sie auf einem Eigenschaftenlistensteuerelement hinzufügen.  Weitere Informationen finden Sie unter [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
 Ein Eigenschaftenobjekt kann Datentypen wie Zeichenfolgen, Datumsangaben und boolesche oder ganzzahlige Werte darstellen.  Es kann untergeordnete Eigenschaften enthalten, oder es kann ein Steuerelement wie ein Kombinationsfeld oder ein Schaltflächen\-Steuerelement enthalten.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `CMFCPropertyGridProperty`\-Objekt erstellt.  Das Beispiel zeigt auch, wie verschiedene Methoden in der `CMFCPropertyGridProperty`\-Klasse verwendet, um eine Option hinzuzufügen, ein Unterelement hinzuzufügen, eine Eigenschaft zu aktivieren und eine Eigenschaft anzuzeigen.  Dieses Beispiel ist Teil [Neue Kontrollprobe](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#27](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#27)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
## Anforderungen  
 **Header:** afxpropertygridctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)