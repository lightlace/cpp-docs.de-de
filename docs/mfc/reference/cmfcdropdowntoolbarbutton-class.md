---
title: "CMFCDropDownToolbarButton Class"
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
  - "CMFCDropDownToolbarButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownToolbarButton class"
  - "OnCancelMode method"
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
caps.latest.revision: 31
caps.handback.revision: "20"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownToolbarButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Typ Symbolleistenschaltfläche, die wie eine normale Schaltfläche verhält, wenn darauf geklickt wird.  jedoch öffnet sie eine Dropdownsymbolleiste \([CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md), wenn der Benutzer die Symbolleistenschaltfläche herunterdrückt und enthält.  
  
## Syntax  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../Topic/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton.md)|Erstellt ein `CMFCDropDownToolbarButton`\-Objekt.|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CopyFrom](../Topic/CMFCDropDownToolbarButton::CopyFrom.md)|Kopiert die Eigenschaften einer anderen Symbolleisten\-Schaltfläche zur aktuellen Schaltfläche.  \(Überschreibungen [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md).\)|  
|`CMFCDropDownToolbarButton::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCDropDownToolbarButton::DropDownToolbar](../Topic/CMFCDropDownToolbarButton::DropDownToolbar.md)|Öffnet eine Dropdown\-Symbolleiste.|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](../Topic/CMFCDropDownToolbarButton::ExportToMenuButton.md)|Kopien Text aus der Symbolleisten\-Schaltfläche zu einem Menü.  \(Überschreibungen [CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md).\)|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](../Topic/CMFCDropDownToolbarButton::GetDropDownToolBar.md)|Ruft die Dropdown\-Symbolleiste ab, die mit der Schaltfläche zugeordnet ist.|  
|`CMFCDropDownToolbarButton::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCDropDownToolbarButton::IsDropDown](../Topic/CMFCDropDownToolbarButton::IsDropDown.md)|Bestimmt, ob die Dropdown\-Symbolleiste geöffnet ist.|  
|[CMFCDropDownToolbarButton::IsExtraSize](../Topic/CMFCDropDownToolbarButton::IsExtraSize.md)|Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann.  \(Überschreibungen [CMFCToolBarButton::IsExtraSize](../Topic/CMFCToolBarButton::IsExtraSize.md).\)|  
|[CMFCDropDownToolbarButton::OnCalculateSize](../Topic/CMFCDropDownToolbarButton::OnCalculateSize.md)|Aufgerufen vom Framework, um die Größe der Schaltfläche für den angegebenen Gerätekontext und den angedockten Zustand zu berechnen.  \(Überschreibungen [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md).\)|  
|`CMFCDropDownToolbarButton::OnCancelMode`|Aufgerufen vom Framework, um die [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) Meldung zu bearbeiten.  \(Überschreibungen `CMCToolBarButton::OnCancelMode`.\)|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](../Topic/CMFCDropDownToolbarButton::OnChangeParentWnd.md)|Aufgerufen vom Framework, wenn die Schaltfläche in eine neue Symbolleiste eingefügt wird.  \(Überschreibungen [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md).\)|  
|[CMFCDropDownToolbarButton::OnClick](../Topic/CMFCDropDownToolbarButton::OnClick.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Maustaste klickt.  \(Überschreibungen [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md).\)|  
|[CMFCDropDownToolbarButton::OnClickUp](../Topic/CMFCDropDownToolbarButton::OnClickUp.md)|Aufgerufen vom Framework, wenn der Benutzer die Maustaste loslässt.  \(Überschreibungen [CMFCToolBarButton::OnClickUp](../Topic/CMFCToolBarButton::OnClickUp.md).\)|  
|[CMFCDropDownToolbarButton::OnContextHelp](../Topic/CMFCDropDownToolbarButton::OnContextHelp.md)|Aufgerufen vom Framework, wenn die Elemente eine Symbolleiste `WM_HELPHITTEST` Meldung verarbeitet.  \(Überschreibungen [CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md).\)|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](../Topic/CMFCDropDownToolbarButton::OnCustomizeMenu.md)|Ändert das bereitgestellte Menü, wenn die Anwendung ein Kontextmenü auf der übergeordneten Symbolleiste angezeigt wird.  \(Überschreibungen [CMFCToolBarButton::OnCustomizeMenu](../Topic/CMFCToolBarButton::OnCustomizeMenu.md).\)|  
|[CMFCDropDownToolbarButton::OnDraw](../Topic/CMFCDropDownToolbarButton::OnDraw.md)|Aufgerufen durch das Framework, um die Schaltfläche mithilfe der angegebenen Formate und der Optionen zu zeichnen.  \(Überschreibungen [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md).\)|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](../Topic/CMFCDropDownToolbarButton::OnDrawOnCustomizeList.md)|Aufgerufen durch das Framework, um die Schaltfläche im Bereich **Befehle** des Dialogfelds **Anpassen** zu zeichnen.  \(Überschreibungen [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md).\)|  
|[CMFCDropDownToolbarButton::Serialize](../Topic/CMFCDropDownToolbarButton::Serialize.md)|Liest dieses Objekt einem Archiv oder schreibt es einem Archiv.  \(Überschreibungen [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md).\)|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](../Topic/CMFCDropDownToolbarButton::SetDefaultCommand.md)|Legt den Standardbefehl fest, das vom Framework verwendet, wenn ein Benutzer auf die Schaltfläche klickt.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::m\_uiShowBarDelay](../Topic/CMFCDropDownToolbarButton::m_uiShowBarDelay.md)|Gibt die Zeitspanne an, dass ein Benutzer die Maustaste gedrückt halten muss, bevor die Dropdown\-Symbolleiste angezeigt wird.|  
  
## Hinweise  
 `CMFCDropDownToolBarButton` unterscheidet sich von einer normalen Schaltfläche darin, dass sie einen kleinen Pfeil in der rechten unteren Ecke der Schaltfläche verfügt.  Nachdem der Benutzer eine Schaltfläche von der Dropdown\-Symbolleiste auswählt, zeigt das Framework sein Symbol auf der Symbolleisten\-Schaltfläche der obersten Ebene \(Schaltfläche mit dem kleinen Pfeil in der rechten unteren Ecke\).  
  
 Informationen darüber, wie eine Dropdown\-Symbolleiste, finden Sie unter [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md) implementiert.  
  
 Das Objekt kann `CMFCDropDownToolBarButton` exportiert werden zu einem [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md)\-Objekt und als Menüschaltfläche mit einem Popupmenü angezeigt werden.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## Anforderungen  
 **Header:**  afxdropdowntoolbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)