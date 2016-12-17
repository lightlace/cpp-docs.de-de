---
title: "CMFCToolBarFontSizeComboBox Class"
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
  - "CMFCToolBarFontSizeComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarFontSizeComboBox class"
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
caps.latest.revision: 26
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarFontSizeComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Symbolleistenschaltfläche, die ein Kombinationsfeld\-Steuerelement enthält, das dem Benutzer ermöglicht, um einen Schriftgrad auszuwählen.  
  
## Syntax  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](../Topic/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox.md)|Erstellt ein `CMFCToolBarFontSizeComboBox`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](../Topic/CMFCToolBarFontSizeComboBox::GetTwipSize.md)|Gibt den Schriftgrad in den ausgewählten Twipien zurück.|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](../Topic/CMFCToolBarFontSizeComboBox::RebuildFontSizes.md)|Füllt die Kombinationsfeldliste mit allen unterstützten Schriftgraden für eine angegebene Schriftart aus.|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](../Topic/CMFCToolBarFontSizeComboBox::SetTwipSize.md)|Legt den Schriftgrad in den Twipien fest.|  
  
## Hinweise  
 Sie können ein Objekt `CMFCToolBarFontSizeComboBox` zusammen mit einem [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md)\-Objekt verwenden, um einen Benutzer zu ermöglichen, eine Schriftart und einen Schriftgrad auszuwählen.  
  
 Sie können eine Schriftgradkombinationsfeldschaltfläche einer Symbolleiste hinzufügen, wie Sie eine Schriftartkombinationsfeldschaltfläche hinzufügen.  Weitere Informationen finden Sie unter [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
 Wenn der Benutzer eine neue Schriftart in einem `CMFCToolBarFontComboBox`\-Objekt abruft, können Sie das Schriftgradkombinationsfeld mit den unterstützten Größen für diese Schriftart ausfüllen, indem Sie die Methode verwenden. [CMFCToolBarFontSizeComboBox::RebuildFontSizes](../Topic/CMFCToolBarFontSizeComboBox::RebuildFontSizes.md)  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der `CMFCToolBarFontSizeComboBox`\-Klasse verwendet, um ein `CMFCToolBarFontSizeComboBox`\-Objekt zu konfigurieren.  Das Beispiel veranschaulicht, wie die Schriftgröße, in den Twipien, vom Textfeld abgerufen werden, füllt das Schriftgradkombinationsfeld mit allen gültigen Größen der angegebenen Schriftarten aus und gibt den Schriftgrad in den Twipien an.  Dieser Codeausschnitt ist Teil [Word\-Auflagenbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_WordPad#8](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_WordPad#8)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)  
  
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