---
title: "CMFCRibbonComboBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonComboBox class"
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCRibbonComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCRibbonComboBox`\-Klasse implementiert ein Kombinationsfeld\-Steuerelement, das Sie einer Menübandleiste, einem Favoritenmenübandbereich oder einem Menübandpopupmenü hinzufügen können.  
  
## Syntax  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## Mitglieder  
  
### Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](../Topic/CMFCRibbonComboBox::CMFCRibbonComboBox.md)|Erstellt ein CMFCRibbonComboBox\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonComboBox::AddItem](../Topic/CMFCRibbonComboBox::AddItem.md)|Fügt ein Unikat dem Listenfeld an.|  
|[CMFCRibbonComboBox::DeleteItem](../Topic/CMFCRibbonComboBox::DeleteItem.md)|Löscht ein angegebenes Element aus dem Listenfeld.|  
|[CMFCRibbonComboBox::EnableDropDownListResize](../Topic/CMFCRibbonComboBox::EnableDropDownListResize.md)|Gibt an, ob das Listenfeld Größe ändern kann, wenn unten ablegt.|  
|[CMFCRibbonComboBox::FindItem](../Topic/CMFCRibbonComboBox::FindItem.md)|Gibt den Index des ersten Elements im Listenfeld zurück, das eine angegebene Zeichenfolge.|  
|[CMFCRibbonComboBox::GetCount](../Topic/CMFCRibbonComboBox::GetCount.md)|Gibt die Anzahl der Elemente im Listenfeld zurück.|  
|[CMFCRibbonComboBox::GetCurSel](../Topic/CMFCRibbonComboBox::GetCurSel.md)|Ruft den Index des aktuell ausgewählten Elements im Listenfeld ab.|  
|[CMFCRibbonComboBox::GetDropDownHeight](../Topic/CMFCRibbonComboBox::GetDropDownHeight.md)|Ruft die Höhe des Listenfelds ab, wenn das Listenfeld unten abgelegt wird.|  
|[CMFCRibbonComboBox::GetIntermediateSize](../Topic/CMFCRibbonComboBox::GetIntermediateSize.md)|Gibt die Größe des Kombinationsfelds zurück, wie aus dem Modus angezeigt.|  
|[CMFCRibbonComboBox::GetItem](../Topic/CMFCRibbonComboBox::GetItem.md)|Gibt die Zeichenfolge zurück, die einem Element zu einem angegebenen Index im Listenfeld zugeordnet ist.|  
|[CMFCRibbonComboBox::GetItemData](../Topic/CMFCRibbonComboBox::GetItemData.md)|Gibt die Daten zurück, die einem Element zu einem angegebenen Index im Listenfeld zugeordnet werden.|  
|[CMFCRibbonComboBox::HasEditBox](../Topic/CMFCRibbonComboBox::HasEditBox.md)|Gibt an, ob das Steuerelement ein Eingabefeld enthält.|  
|[CMFCRibbonComboBox::IsResizeDropDownList](../Topic/CMFCRibbonComboBox::IsResizeDropDownList.md)|Gibt an, ob das Listenfeld Größe geändert werden kann.|  
|[CMFCRibbonComboBox::OnSelectItem](../Topic/CMFCRibbonComboBox::OnSelectItem.md)|Aufgerufen vom Framework, wenn der Benutzer ein Element im Listenfeld aus.|  
|[CMFCRibbonComboBox::RemoveAllItems](../Topic/CMFCRibbonComboBox::RemoveAllItems.md)|Löscht alle Elemente im Listenfeld und löscht das Eingabefeld.|  
|[CMFCRibbonComboBox::SelectItem](../Topic/CMFCRibbonComboBox::SelectItem.md)|Wählt ein Element im Listenfeld aus.|  
|[CMFCRibbonComboBox::SetDropDownHeight](../Topic/CMFCRibbonComboBox::SetDropDownHeight.md)|Gibt die Höhe des Listenfelds fest, wenn sie unten abgelegt wird.|  
  
## Hinweise  
 Das Menübandkombinationsfeld besteht aus einem Listenfeld, das entweder mit einer statische Bezeichnung oder Beschriftung, die kombiniert, wird vom Benutzer bearbeitet werden können.  Sie müssen angeben, die gewünschten eingeben, wenn Sie das Menübandkombinationsfeld erstellen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt der Klasse `CMFCRibbonComboBox` erstellt, ein Element dem Kombinationsfeld hinzufügt, ein Element im Kombinationsfeld auswählt und ein Kombinationsfeld einem Bereich hinzufügt.  
  
 [!CODE [NVC_MFC_RibbonApp#11](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#11)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## Anforderungen  
 **Header:** afxribboncombobox.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonEdit Class](../../mfc/reference/cmfcribbonedit-class.md)