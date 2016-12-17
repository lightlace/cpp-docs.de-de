---
title: "CMFCFontComboBox Class"
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
  - "CMFCFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCFontComboBox class"
  - "CMFCFontComboBox::CompareItem method"
  - "CMFCFontComboBox::DrawItem method"
  - "CMFCFontComboBox::MeasureItem method"
  - "CMFCFontComboBox::PreTranslateMessage method"
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
caps.latest.revision: 29
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCFontComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCFontComboBox`\-Klasse erstellt ein Kombinationsfeld\-Steuerelement, das eine Liste von Schriftarten enthält.  
  
## Syntax  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFontComboBox::CMFCFontComboBox](../Topic/CMFCFontComboBox::CMFCFontComboBox.md)|Erstellt ein `CMFCFontComboBox`\-Objekt.|  
|`CMFCFontComboBox::~CMFCFontComboBox`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCFontComboBox::CompareItem`|Aufgerufen vom Framework, um die relative Position eines neuen Elements im sortierten Listenfeld des aktuellen Schriftartkombinationsfeld\-steuerelements zu bestimmen.  \(Überschreibungen [CComboBox::CompareItem](../Topic/CComboBox::CompareItem.md).\)|  
|`CMFCFontComboBox::DrawItem`|Aufgerufen vom Framework, um ein bestimmtes Element im aktuellen Schriftartkombinationsfeld\-steuerelement zu zeichnen.  \(Überschreibungen [CComboBox::DrawItem](../Topic/CComboBox::DrawItem.md).\)|  
|[CMFCFontComboBox::GetSelFont](../Topic/CMFCFontComboBox::GetSelFont.md)|Ruft Informationen über die aktuell ausgewählte Schriftart ab.|  
|`CMFCFontComboBox::MeasureItem`|Aufgerufen vom Framework, um Windows über die Abmessungen des Listenfelds im aktuellen Schriftartkombinationsfeld\-steuerelement zu informieren.  \(Überschreibungen [CComboBox::MeasureItem](../Topic/CComboBox::MeasureItem.md).\)|  
|`CMFCFontComboBox::PreTranslateMessage`|Übersetzt Fenstermeldungen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  \(Überschreibungen [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCFontComboBox::SelectFont](../Topic/CMFCFontComboBox::SelectFont.md)|Wählt die Schriftart aus, die die angegebenen Kriterien vom Schriftartkombinationsfeld übereinstimmt.|  
|[CMFCFontComboBox::Setup](../Topic/CMFCFontComboBox::Setup.md)|Initialisiert die Liste der Elemente im Schriftartkombinationsfeld.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFontComboBox::m\_bDrawUsingFont](../Topic/CMFCFontComboBox::m_bDrawUsingFont.md)|Gibt das Framework an, das die Schriftart, um zu verwenden, um das Element zu zeichnen im aktuellen Schriftartkombinationsfeld bezeichnet.|  
  
## Hinweise  
 Um ein `CMFCFontComboBox`\-Objekt in einem Dialogfeld zu verwenden, fügen Sie eine `CMFCFontComboBox`\-Variable der Dialogfeldklasse hinzu.  In der `OnInitDialog`\-Methode Dialogklasse, rufen Sie die [CMFCFontComboBox::Setup](../Topic/CMFCFontComboBox::Setup.md)\-Methode auf, um die Liste der Elemente im Kombinationsfeld zu initialisieren.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## Anforderungen  
 **Header:** afxfontcombobox.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md)