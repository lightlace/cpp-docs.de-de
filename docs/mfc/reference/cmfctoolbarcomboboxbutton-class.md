---
title: "CMFCToolBarComboBoxButton Class"
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
  - "CMFCToolBarComboBoxButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarComboBoxButton class"
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
caps.latest.revision: 30
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarComboBoxButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Symbolleistenschaltfläche, die ein Kombinationsfeld\-Steuerelement \([CComboBox Class](../../mfc/reference/ccombobox-class.md)\) enthält.  
  
## Syntax  
  
```  
class CMFCToolBarComboBoxButton : public CMFCToolBarButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](../Topic/CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton.md)|Erstellt einen `CMFCToolBarComboBoxButton`.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::AddItem](../Topic/CMFCToolBarComboBoxButton::AddItem.md)|Fügt ein Element am Ende der Kombinationsfeldliste hinzu.|  
|[CMFCToolBarComboBoxButton::AddSortedItem](../Topic/CMFCToolBarComboBoxButton::AddSortedItem.md)|Fügt ein Element der Kombinationsfeldliste hinzu.  Die Reihenfolge der Elemente in der Liste wird durch `Compare` angegeben.|  
|[CMFCToolBarComboBoxButton::Compare](../Topic/CMFCToolBarComboBoxButton::Compare.md)|Vergleicht zwei Elemente.  Aufgerufen sortieren, wenn Elemente, die `AddSortedItems` der Kombinationsfeldliste hinzugefügt wird.|  
|[CMFCToolBarComboBoxButton::CreateEdit](../Topic/CMFCToolBarComboBoxButton::CreateEdit.md)|Erstellt ein neues Bearbeitungssteuerelement für die Kombinationsfeldschaltfläche.|  
|[CMFCToolBarComboBoxButton::DeleteItem](../Topic/CMFCToolBarComboBoxButton::DeleteItem.md)|Löscht ein Element aus der Kombinationsfeldliste.|  
|[CMFCToolBarComboBoxButton::FindItem](../Topic/CMFCToolBarComboBoxButton::FindItem.md)|Gibt den Index des Elements zurück, das eine angegebene Zeichenfolge enthält.|  
|[CMFCToolBarComboBoxButton::GetByCmd](../Topic/CMFCToolBarComboBoxButton::GetByCmd.md)|Gibt einen Zeiger auf die Kombinationsfeldschaltfläche mit einer angegebenen Befehl ID zurück|  
|[CMFCToolBarComboBoxButton::GetComboBox](../Topic/CMFCToolBarComboBoxButton::GetComboBox.md)|Gibt einen Zeiger auf Kombinationsfeld\-Steuerelement zurück, das in der Kombinationsfeldschaltfläche eingebettet ist.|  
|[CMFCToolBarComboBoxButton::GetCount](../Topic/CMFCToolBarComboBoxButton::GetCount.md)|Gibt die Anzahl der Elemente in der Kombinationsfeldliste zurück.|  
|[CMFCToolBarComboBoxButton::GetCountAll](../Topic/CMFCToolBarComboBoxButton::GetCountAll.md)|Sucht die Kombinationsfeldschaltfläche, die eine angegebene Befehl ID besitzt  Gibt die Anzahl der Elemente in der Kombinationsfeldliste dieser Schaltfläche zurück.|  
|[CMFCToolBarComboBoxButton::GetCurSel](../Topic/CMFCToolBarComboBoxButton::GetCurSel.md)|Gibt den Index des ausgewählten Elements in der Kombinationsfeldliste zurück.|  
|[CMFCToolBarComboBoxButton::GetCurSelAll](../Topic/CMFCToolBarComboBoxButton::GetCurSelAll.md)|Sucht die Kombinationsfeldschaltfläche, die eine angegebene Befehls\-ID verfügt, und gibt den Index des ausgewählten Elements in der Kombinationsfeldliste dieser Schaltfläche zurück.|  
|[CMFCToolBarComboBoxButton::GetEditCtrl](../Topic/CMFCToolBarComboBoxButton::GetEditCtrl.md)|Gibt einen Zeiger auf das Bearbeitungssteuerelement zurück, das in der Kombinationsfeldschaltfläche eingebettet ist.|  
|[CMFCToolBarComboBoxButton::GetItem](../Topic/CMFCToolBarComboBoxButton::GetItem.md)|Gibt die Zeichenfolge zurück, die einem angegebenen Index in der Kombinationsfeldliste zugeordnet ist.|  
|[CMFCToolBarComboBoxButton::GetItemAll](../Topic/CMFCToolBarComboBoxButton::GetItemAll.md)|Sucht die Kombinationsfeldschaltfläche, die eine angegebene Befehls\-ID verfügt, und gibt die Zeichenfolge zurück, die mit einem Index in der Kombinationsfeldliste dieser Schaltfläche zugeordnet ist.|  
|[CMFCToolBarComboBoxButton::GetItemData](../Topic/CMFCToolBarComboBoxButton::GetItemData.md)|Gibt den 32\-Bit\-Wert zurück, der mit einem angegebenen Index in der Kombinationsfeldliste zugeordnet ist.|  
|[CMFCToolBarComboBoxButton::GetItemDataAll](../Topic/CMFCToolBarComboBoxButton::GetItemDataAll.md)|Sucht die Kombinationsfeldschaltfläche, die eine angegebene Befehls\-ID verfügt, und gibt den 32\-Bit\-Wert zurück, der mit einem Index in der Kombinationsfeldliste dieser Schaltfläche zugeordnet ist.|  
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](../Topic/CMFCToolBarComboBoxButton::GetItemDataPtrAll.md)|Sucht die Kombinationsfeldschaltfläche, die eine angegebene Befehl ID besitzt  Ruft den 32\-Bit\-Wert, dem ein Index in der Kombinationsfeldliste dieser Schaltfläche zugeordnet ist, und gibt den 32\-Bit\-Wert als Zeiger zurück.|  
|[CMFCToolBarComboBoxButton::GetText](../Topic/CMFCToolBarComboBoxButton::GetText.md)|Gibt den Text vom Bearbeitungssteuerelement des Kombinationsfelds zurück.|  
|[CMFCToolBarComboBoxButton::GetTextAll](../Topic/CMFCToolBarComboBoxButton::GetTextAll.md)|Sucht die Kombinationsfeldschaltfläche, die eine angegebene Befehls\-ID verfügt, und gibt den Text vom Bearbeitungssteuerelement dieser Schaltfläche zurück.|  
|[CMFCToolBarComboBoxButton::IsCenterVert](../Topic/CMFCToolBarComboBoxButton::IsCenterVert.md)|Bestimmt, ob Kombinationsfeldschaltflächen in der Anwendung mit der Anfang der Symbolleiste oder zentriert ausgerichtet sind.|  
|[CMFCToolBarComboBoxButton::IsFlatMode](../Topic/CMFCToolBarComboBoxButton::IsFlatMode.md)|Bestimmt, ob Kombinationsfeldschaltflächen in der Anwendung eine flache Darstellung haben.|  
|[CMFCToolBarComboBoxButton::RemoveAllItems](../Topic/CMFCToolBarComboBoxButton::RemoveAllItems.md)|Entfernt alle Elemente aus dem Listenfeld und vom Bearbeitungssteuerelement des Kombinationsfelds.|  
|[CMFCToolBarComboBoxButton::SelectItem](../Topic/CMFCToolBarComboBoxButton::SelectItem.md)|Wählt ein Element im Kombinationsfeld entsprechend dem Index, 32\-Bit\-Wert oder Zeichenfolge aus und setzt das Kombinationsfeld\-Steuerelement zur Auswahl.|  
|[CMFCToolBarComboBoxButton::SelectItemAll](../Topic/CMFCToolBarComboBoxButton::SelectItemAll.md)|Sucht die Kombinationsfeldschaltfläche, die eine angegebene Befehl ID besitzt  Ruft `SelectItem` auf, um ein Element im Kombinationsfeld dieser Schaltfläche entsprechend ihrer Zeichenfolge, Index oder 32\-Bit\-Wert auszuwählen.|  
|[CMFCToolBarComboBoxButton::SetCenterVert](../Topic/CMFCToolBarComboBoxButton::SetCenterVert.md)|Gibt an, ob Kombinationsfeldschaltflächen in der Anwendung vertikal zentriert sind oder mit der Anfang der Symbolleiste ausgerichtet.|  
|[CMFCToolBarComboBoxButton::SetDropDownHeight](../Topic/CMFCToolBarComboBoxButton::SetDropDownHeight.md)|Gibt die Höhe des Dropdown\-Listenfelds fest.|  
|[CMFCToolBarComboBoxButton::SetFlatMode](../Topic/CMFCToolBarComboBoxButton::SetFlatMode.md)|Gibt an, ob Kombinationsfeldschaltflächen in der Anwendung eine flache Darstellung haben.|  
  
## Hinweise  
 Um eine Kombinationsfeldschaltfläche einer Symbolleiste hinzuzufügen, führen Sie folgende Schritte aus:  
  
 1.  Reservieren Sie ein blindes Ressourcen\-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
 2.  Konstruieren Sie ein `CMFCToolBarComboBoxButton`\-Objekt.  
  
 3.  Im Meldungshandler, der die `AFX_WM_RESETTOOLBAR` Meldung verarbeitet, ersetzen Sie die blinde Schaltfläche durch die neue Kombinationsfeldschaltfläche, indem Sie [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) verwenden.  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md).  Ein Beispiel einer Kombinationsfeldsymbolleistenschaltfläche, finden Sie das Beispielprojekt VisualStudioDemo.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCToolBarComboBoxButton` verwendet.  Im Beispiel wird gezeigt, wie die Bearbeitung und Kombinationsfeldern, legen Sie die vertikale Position von Kombinationsfeldschaltflächen in der Anwendung, legen Sie die Höhe des Listenfelds, wenn sie unten abgelegt wird, legen Sie die flache Darstellung von Kombinationsfeldschaltflächen in der Anwendung und legen Sie den Text im Eingabefeld der Kombinationsfeldschaltfläche aktiviert.  Dieser Codeausschnitt ist Teil [Visual Studio\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_VisualStudioDemo#36](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#36)]  
[!CODE [NVC_MFC_VisualStudioDemo#37](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#37)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
## Anforderungen  
 **Header:** afxtoolbarcomboboxbutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)