---
title: "CMFCRibbonSeparator Class"
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
  - "GetThisClass"
  - "CMFCRibbonSeparator::GetThisClass"
  - "CMFCRibbonSeparator.CreateObject"
  - "CMFCRibbonSeparator::CreateObject"
  - "CMFCRibbonSeparator"
  - "CreateObject"
  - "CMFCRibbonSeparator.GetThisClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonSeparator class"
  - "CreateObject method"
  - "GetThisClass method"
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonSeparator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert das Menübandtrennzeichen.  
  
## Syntax  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](../Topic/CMFCRibbonSeparator::CMFCRibbonSeparator.md)|Erstellt ein `CMFCRibbonSeparator`\-Objekt.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCRibbonSeparator::AddToListBox](../Topic/CMFCRibbonSeparator::AddToListBox.md)|Fügt ein Trennzeichen **Befehle** der Liste im Dialogfeld **Anpassen** hinzu.  \(Überschreibungen [CMFCRibbonBaseElement::AddToListBox](../Topic/CMFCRibbonBaseElement::AddToListBox.md).\)|  
|`CMFCRibbonSeparator::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCRibbonSeparator::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
  
### Geschützte Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCRibbonSeparator::CopyFrom](../Topic/CMFCRibbonSeparator::CopyFrom.md)|Eine Copy\-Methode, die die Membervariablen eines Trennzeichens aus einem anderen Objekt festgelegt wird.|  
|[CMFCRibbonSeparator::GetRegularSize](../Topic/CMFCRibbonSeparator::GetRegularSize.md)|Gibt die Größe eines Trennzeichens zurück.|  
|[CMFCRibbonSeparator::IsSeparator](../Topic/CMFCRibbonSeparator::IsSeparator.md)|Gibt an, ob dies ein Trennzeichen ist.|  
|[CMFCRibbonSeparator::IsTabStop](../Topic/CMFCRibbonSeparator::IsTabStop.md)|Gibt an, ob dies ein Tabstopp ist.|  
|[CMFCRibbonSeparator::OnDraw](../Topic/CMFCRibbonSeparator::OnDraw.md)|Aufgerufen vom System, um das Trennzeichen entweder im Menüband oder der Symbolleiste für den Schnellzugriff zu zeichnen.|  
|[CMFCRibbonSeparator::OnDrawOnList](../Topic/CMFCRibbonSeparator::OnDrawOnList.md)|Aufgerufen vom System, um das Trennzeichen auf der Liste **Befehle** zu zeichnen.|  
  
## Hinweise  
 Ein Menübandtrennzeichen ist eine vertikale oder eine horizontale Linie, die logisch Menübandelemente trennt.  Ein Trennzeichen kann auf dem Menüband\-Steuerelement, dem Hauptanwendungsmenü, der Menübandstatusleiste und der Symbolleiste für den Schnellzugriff gezeichnet werden.  
  
 Um ein Trennzeichen in der Anwendung zu verwenden, erstellen Sie das neue Objekt und fügen Sie es dem Hauptanwendungsmenü wie folgt hinzu:  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"), IDB_FILESMALL, IDB_FILELARGE);   
...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));  
```  
  
 Rufen Sie [CMFCRibbonPanel::AddSeparator](../Topic/CMFCRibbonPanel::AddSeparator.md) auf, um Trennzeichen Menübandbereichen hinzuzufügen.  Die Trennzeichen werden intern von der `AddSeparator`\-Methode zugeordnet und hinzugefügt.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## Anforderungen  
 **Header:** afxbaseribbonelement.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)