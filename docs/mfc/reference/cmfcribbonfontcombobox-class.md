---
title: "CMFCRibbonFontComboBox Class"
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
  - "CMFCRibbonFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonFontComboBox class"
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonFontComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert ein Kombinationsfeld, das eine Liste von Schriftarten enthält.  Das Kombinationsfeld kann in einem Menübandbereich platziert werden.  
  
## Syntax  
  
```  
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Destruktor.|  
  
### Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](../Topic/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox.md)|Erstellt und initialisiert ein `CMFCRibbonFontComboBox`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCRibbonFontComboBox::BuildFonts](../Topic/CMFCRibbonFontComboBox::BuildFonts.md)|Füllt das Schriftartkombinationsfeld für das Menüband mit Schriftarten des angegebenen Schriftarttyps, Zeichensatzes, der Zeichenbreite und Schriftfamilie auf.|  
|`CMFCRibbonFontComboBox::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCRibbonFontComboBox::GetCharSet](../Topic/CMFCRibbonFontComboBox::GetCharSet.md)|Gibt den angegebenen Zeichensatz zurück.|  
|[CMFCRibbonFontComboBox::GetFontDesc](../Topic/CMFCRibbonFontComboBox::GetFontDesc.md)||  
|[CMFCRibbonFontComboBox::GetFontType](../Topic/CMFCRibbonFontComboBox::GetFontType.md)|Gibt zurück, welche Schriftarttypen im Kombinationsfeld angezeigt werden.  Gültige Optionen sind DEVICE\_FONTTYPE, RASTER\_FONTTYPE, und TRUETYPE\_FONTTYPE oder jede bitweise Kombination davon.|  
|[CMFCRibbonFontComboBox::GetPitchAndFamily](../Topic/CMFCRibbonFontComboBox::GetPitchAndFamily.md)|Gibt die Schriftbreite und Schriftfamilie der Schriftarten zurück, die im Kombinationsfeld angezeigt werden.|  
|`CMFCRibbonFontComboBox::GetThisClass`|Wird vom Framework verwendet wird, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCRibbonFontComboBox::RebuildFonts](../Topic/CMFCRibbonFontComboBox::RebuildFonts.md)|Füllt das Schriftartkombinationsfeld für das Menüband mit Schriftarten des zuvor angegebenen Schriftarttyps, Zeichensatzes, der Zeichenbreite und Schriftfamilie auf.|  
|[CMFCRibbonFontComboBox::SetFont](../Topic/CMFCRibbonFontComboBox::SetFont.md)|Wählt die angegebene Schriftart im Kombinationsfeld aus.|  
  
## Hinweise  
 Nachdem Sie ein `CMFCRibbonFontComboBox`\-Objekt erstellt haben, können Sie es mithilfe des Aufrufs [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md) zum Menübandbereich hinzufügen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)  
  
## Anforderungen  
 **Header:** afxRibbonComboBox.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonComboBox Class](../../mfc/reference/cmfcribboncombobox-class.md)