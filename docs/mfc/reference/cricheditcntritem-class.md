---
title: "CRichEditCntrItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRichEditCntrItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCntrItem class"
  - "OLE items, in rich edit views"
  - "Rich-Edit-Steuerelemente, OLE items"
  - "Rich-Edit-Steuerelemente, Verwenden"
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CRichEditCntrItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit [CRichEditView](../../mfc/reference/cricheditview-class.md) und [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) stellt die Funktionalität des Rich\-Edit\-Steuerelements im Kontext Dokumenten\-Ansichtsarchitektur MFC bereit.  
  
## Syntax  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](../Topic/CRichEditCntrItem::CRichEditCntrItem.md)|Erstellt ein `CRichEditCntrItem`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](../Topic/CRichEditCntrItem::SyncToRichEditObject.md)|Ermöglicht das Element als anderer Typ.|  
  
## Hinweise  
 Ein "RichEdit\-Steuerelement" ist ein Fenster, in dem der Benutzer Text eingeben und bearbeiten kann.  Der Text kann Zeichen und Absatzformatierung zugewiesen und kann eingebettete OLE\-Objekte einschließen.  derzeit stellen eine Programmierschnittstelle zum Formatieren von Text bereit.  muss jedoch eine Anwendung alle Benutzeroberflächenkomponenten implementieren, die erforderlich sind, Formatierungsvorgänge zu machen für den Benutzer.  
  
 `CRichEditView` verwaltet das Text\- und Formatierungseigenschaft des Texts bei.  `CRichEditDoc` führt die Liste der OLE\-Clientelementen, die in der Ansicht sind.  `CRichEditCntrItem` ContainerSeite bietet Zugriff auf OLE\-Clientelement.  
  
 Dieses allgemeine Windows\-Steuerelement \(und daher [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und die zugehörigen Klassen\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT\-Versionen 3,51 und höher ausgeführt werden.  
  
 Ein Beispiel für die Verwendung von zahlreichen bearbeiten Sie Containerelemente in einer MFC\-Anwendung, finden die [WORDPAD](../../top/visual-cpp-samples.md) Beispielanwendung.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## Anforderungen  
 **Header:**  afxrich.h  
  
## Siehe auch  
 [MFC\-Beispiel WORDPAD](../../top/visual-cpp-samples.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc Class](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)