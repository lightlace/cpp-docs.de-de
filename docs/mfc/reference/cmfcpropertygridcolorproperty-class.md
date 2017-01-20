---
title: "CMFCPropertyGridColorProperty Class"
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
  - "CMFCPropertyGridColorProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridColorProperty class"
  - "CMFCPropertyGridColorProperty::FormatProperty method"
  - "CMFCPropertyGridColorProperty::OnClickButton method"
  - "CMFCPropertyGridColorProperty::OnDrawValue method"
  - "CMFCPropertyGridColorProperty::OnEdit method"
  - "CMFCPropertyGridColorProperty::OnUpdateValue method"
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
caps.latest.revision: 33
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridColorProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCPropertyGridColorProperty`\-Klasse unterstützt ein Eigenschaftslisten\-Steuerelement, über das ein Farbauswahl\-Dialogfeld geöffnet werden kann.  
  
## Syntax  
  
```  
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](../Topic/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty.md)|Erstellt ein `CMFCPropertyGridColorProperty`\-Objekt.|  
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](../Topic/CMFCPropertyGridColorProperty::EnableAutomaticButton.md)|Aktiviert die Schaltfläche *automatisch* im Dialogfeld zur Farbauswahl.  \(Standardmäßig  hat Schaltfläche "Automatisch" die Bezeichnung **automatisch**\).|  
|[CMFCPropertyGridColorProperty::EnableOtherButton](../Topic/CMFCPropertyGridColorProperty::EnableOtherButton.md)|Aktiviert die Schaltfläche *sonstige* im Dialogfeld zur Farbauswahl.  \(Standardmäßig hat die Schaltfläche „sonstige“ die Bezeichnung **Weitere Farben...**\).|  
|`CMFCPropertyGridColorProperty::FormatProperty`|Formatiert die Textdarstellung eines Eigenschaftswerts.  \(Überschreibt [CMFCPropertyGridProperty::FormatProperty](../Topic/CMFCPropertyGridProperty::FormatProperty.md).\)|  
|[CMFCPropertyGridColorProperty::GetColor](../Topic/CMFCPropertyGridColorProperty::GetColor.md)|Ruft die aktuelle Farbe der Eigenschaft ab.|  
|`CMFCPropertyGridColorProperty::GetThisClass`|Wird vom Framework verwendet wird, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|`CMFCPropertyGridColorProperty::OnClickButton`|Wird vom Framework aufgerufen, wenn der Benutzer auf eine Schaltfläche klickt, die in einer Eigenschaft enthalten ist.  \(Überschreibt [CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md).\)|  
|`CMFCPropertyGridColorProperty::OnDrawValue`|Wird vom Framework aufgerufen, um die Liste der Eigenschaftenwerte anzuzeigen.  \(Überschreibt [CMFCPropertyGridProperty::OnDrawValue](../Topic/CMFCPropertyGridProperty::OnDrawValue.md).\)|  
|`CMFCPropertyGridColorProperty::OnEdit`|Wird vom Framework aufgerufen, wenn der Benutzer dabei ist, einen Eigenschaftenwert zu bearbeiten.  \(Überschreibt [CMFCPropertyGridProperty::OnEdit](../Topic/CMFCPropertyGridProperty::OnEdit.md).\)|  
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Wird vom Framework aufgerufen, wenn der Wert einer änderbaren Eigenschaft geändert wurde.  \(Überschreibt [CMFCPropertyGridProperty::OnUpdateValue](../Topic/CMFCPropertyGridProperty::OnUpdateValue.md).\)|  
|[CMFCPropertyGridColorProperty::SetColor](../Topic/CMFCPropertyGridColorProperty::SetColor.md)|Legt eine neue Farbe für die Eigenschaft fest.|  
|[CMFCPropertyGridColorProperty::SetColumnsNumber](../Topic/CMFCPropertyGridColorProperty::SetColumnsNumber.md)|Gibt die Anzahl der Spalten in der aktuellen Farbe des Eigenschaftenrasters an.|  
|[CMFCPropertyGridColorProperty::SetOriginalValue](../Topic/CMFCPropertyGridColorProperty::SetOriginalValue.md)|Legt den ursprünglichen Wert einer bearbeitbaren Eigenschaft fest.|  
  
## Hinweise  
 Die `CMFCPropertyGridColorProperty` \-Klasse unterstützt eine Farbeigenschaft, die zu einem Eigenschaftenlisten\-Steuerelement hinzugefügt werden kann.  Weitere Informationen finden Sie unter [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt `CMFCPropertyGridColorProperty`\- Klasse erstellt und mithilfe der verschiedenen Methoden der `CMFCPropertyGridColorProperty`\-Klasse konfiguriert wird.  Der Code erläutert, wie die Schaltflächen „automatisch“ und „sonstige“ aktiviert werden und wie die Farbe und die Spaltenanzahl festgelegt wird.  Dieses Codebeispiel ist Bestandteil des Beispiels unter [Neues Steuerelement\-Beispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#13](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#13)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)  
  
## Anforderungen  
 **Header:** afxpropertygridctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty Class](../../mfc/reference/cmfcpropertygridproperty-class.md)