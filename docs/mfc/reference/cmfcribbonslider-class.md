---
title: "CMFCRibbonSlider Class"
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
  - "CMFCRibbonSlider"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonSlider class"
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
caps.latest.revision: 43
caps.handback.revision: "31"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonSlider Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCRibbonSlider`\-Klasse implementiert ein Schieberegler\-Steuerelement, das Sie einer Menübandleiste oder einer Menübandstatusleiste hinzufügen können.  Das Menübandschieberegler\-steuerelement ähnelt den Zoomschiebereglern, die in den Office 2007\-Anwendungen angezeigt werden.  
  
## Syntax  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](../Topic/CMFCRibbonSlider::CMFCRibbonSlider.md)|erstellt und initialisiert ein Menübandschieberegler\-steuerelement.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonSlider::GetPos](../Topic/CMFCRibbonSlider::GetPos.md)|Gibt die aktuelle Position des Schieberegler\-Steuerelements zurück.|  
|[CMFCRibbonSlider::GetRangeMax](../Topic/CMFCRibbonSlider::GetRangeMax.md)|Gibt den maximalen Wert des Schiebereglers zurück.|  
|[CMFCRibbonSlider::GetRangeMin](../Topic/CMFCRibbonSlider::GetRangeMin.md)|Gibt den minimalen Wert des Schiebereglers zurück.|  
|[CMFCRibbonSlider::GetRegularSize](../Topic/CMFCRibbonSlider::GetRegularSize.md)|Gibt die reguläre Größe des Menübandelements zurück.  \(Überschreibungen [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md).\)|  
|[CMFCRibbonSlider::GetZoomIncrement](../Topic/CMFCRibbonSlider::GetZoomIncrement.md)|Gibt die Größe des Zoominkrements für das Schieberegler\-Steuerelement zurück.|  
|[CMFCRibbonSlider::HasZoomButtons](../Topic/CMFCRibbonSlider::HasZoomButtons.md)|Gibt an, ob der Schieberegler Zoomschaltflächen verfügt.|  
|[CMFCRibbonSlider::OnDraw](../Topic/CMFCRibbonSlider::OnDraw.md)|Aufgerufen durch das Framework, um das Menübandelement zu zeichnen.  \(Überschreibungen [CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md).\)|  
|[CMFCRibbonSlider::SetPos](../Topic/CMFCRibbonSlider::SetPos.md)|Legt die aktuelle Position des Schieberegler\-Steuerelements fest.|  
|[CMFCRibbonSlider::SetRange](../Topic/CMFCRibbonSlider::SetRange.md)|Gibt den Bereich des Schieberegler\-Steuerelements durch Festlegen des Minimums und der maximalen Werte an.|  
|[CMFCRibbonSlider::SetZoomButtons](../Topic/CMFCRibbonSlider::SetZoomButtons.md)|Zeigt die Zoomschaltflächen oder aus.|  
|[CMFCRibbonSlider::SetZoomIncrement](../Topic/CMFCRibbonSlider::SetZoomIncrement.md)|Satzgröße des Zoominkrements für das Schieberegler\-Steuerelement.|  
  
## Hinweise  
 Sie können die `SetRange`\-Methode verwenden, um den Bereich von Zoominkrementen für den Schieberegler zu konfigurieren.  Sie können aktuelle Position des Schiebereglers festlegen, indem Sie die Methode verwenden. `SetPos`  
  
 Sie können zirkuläre Zoomschaltflächen auf der linken und rechten Seite des Schieberegler\-Steuerelements anzeigen, indem Sie die Methode verwenden. `SetZoomButtons` Standardmäßig ist der Schieberegler horizontal, zeigt die linkszoomschaltfläche ein Minuszeichen an und die rechte Zoomschaltfläche wird ein Pluszeichen an.  
  
 Die `SetZoomIncrement`\-Methode definiert das Inkrement, um hinzuzufügen oder von der aktuellen Position zu entfernen, wenn ein Benutzer auf die Zoomschaltflächen klickt.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der `CMFCRibbonSlider`\-Klasse verwendet, um die Eigenschaften des Schiebereglers festzulegen.  Im Beispiel wird gezeigt, wie ein `CMFCRibbonSlider`\-Objekt, Anzeigenzoomschaltflächen, legen Sie die aktuelle Position des Schieberegler\-Steuerelements und legen den Wertebereich für das Schieberegler\-Steuerelement erstellt.  
  
 [!CODE [NVC_MFC_RibbonApp#12](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#12)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## Anforderungen  
 **Header:** afxribbonslider.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)