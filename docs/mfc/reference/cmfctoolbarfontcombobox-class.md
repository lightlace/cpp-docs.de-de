---
title: "CMFCToolBarFontComboBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarFontComboBox class"
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CMFCToolBarFontComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Symbolleistenschaltfläche, die ein Kombinationsfeld\-Steuerelement enthält, das dem Benutzer ermöglicht, eine Schriftart aus einer Liste von Systemschriftarten auszuwählen.  
  
## Syntax  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](../Topic/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox.md)|Erstellt ein `CMFCToolBarFontComboBox`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md)|Gibt einen Zeiger auf `CMFCFontInfo`\-Objekt für einen angegebenen Index im Kombinationsfeld zurück.|  
|[CMFCToolBarFontComboBox::SetFont](../Topic/CMFCToolBarFontComboBox::SetFont.md)|Wählt eine Schriftart im Schriftartkombinationsfeld entweder nach dem Namen der Schriftarten oder das Präfix und der Zeichensatz der Schriftarten aus.|  
  
### Datenmember  
 [CMFCToolBarFontComboBox::m\_nFontHeight](../Topic/CMFCToolBarFontComboBox::m_nFontHeight.md)  
 Die Höhe der Zeichen im Schriftartkombinationsfeld.  
  
## Hinweise  
 Um eine Schriftartkombinationsfeldschaltfläche einer Symbolleiste hinzuzufügen, führen Sie folgende Schritte aus:  
  
1.  Reservieren Sie ein blindes Ressourcen\-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
2.  Konstruieren Sie ein `CMFCToolBarFontComboBox`\-Objekt.  
  
3.  Im Meldungshandler, der die `AFX_WM_RESETTOOLBAR` Meldung verarbeitet, ersetzen Sie die ursprüngliche Schaltfläche durch die neue Kombinationsfeldschaltfläche, indem Sie [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) verwenden.  
  
4.  Synchronisieren Sie die Schriftart, die im Kombinationsfeld mit der Schriftart im Dokument ausgewählt wird, indem die [CMFCToolBarFontComboBox::SetFont](../Topic/CMFCToolBarFontComboBox::SetFont.md)\-Methode erstellt wird.  
  
 Um die Schriftart des Dokuments mit der Schriftart zu synchronisieren, die im Kombinationsfeld ausgewählt wird, verwenden Sie die Methode [CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md) um die Attribute der ausgewählten Schriftarten abzurufen, und verwenden Sie diese Attribute um ein [CFont Class](../../mfc/reference/cfont-class.md)\-Objekt zu erstellen.  
  
 Die Schriftartkombinationsfeldschaltfläche ruft die Win32\-Funktion [EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620) auf, um die Bildschirm\- und Druckerschriftart zu bestimmen, die dem System verfügbar sind.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## Anforderungen  
 **Header:** afxtoolbarfontcombobox.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)