---
title: "CRichEditDoc Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRichEditDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditDoc class"
  - "document/view architecture, Rich-Edit-Steuerelemente"
  - "Dokumente, rich edit"
  - "OLE containers, rich edit"
  - "Rich-Edit-Steuerelemente, OLE container"
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CRichEditDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit [CRichEditView](../../mfc/reference/cricheditview-class.md) und [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) stellt die Funktionalität des Rich\-Edit\-Steuerelements im Kontext Dokumenten\-Ansichtsarchitektur MFC bereit.  
  
## Syntax  
  
```  
  
class CRichEditDoc : public COleServerDoc  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](../Topic/CRichEditDoc::CreateClientItem.md)|Aufgerufen, um Bereinigung des Dokuments auszuführen.|  
|[CRichEditDoc::GetStreamFormat](../Topic/CRichEditDoc::GetStreamFormat.md)|Gibt an, ob Streameingabe und Ausgabe Formatierungsinformationen enthalten sollten.|  
|[CRichEditDoc::GetView](../Topic/CRichEditDoc::GetView.md)|Ruft das asssociated [CRichEditView](../../mfc/reference/cricheditview-class.md)\-Objekt ab.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditDoc::m\_bRTF](../Topic/CRichEditDoc::m_bRTF.md)|Gibt an, ob Stream E\/A Formatierung einschließen soll.|  
  
## Hinweise  
 Ein "RichEdit\-Steuerelement" ist ein Fenster, in dem der Benutzer Text eingeben und bearbeiten kann.  Der Text kann Zeichen und Absatzformatierung zugewiesen und kann eingebettete OLE\-Objekte einschließen.  derzeit stellen eine Programmierschnittstelle zum Formatieren von Text bereit.  muss jedoch eine Anwendung alle Benutzeroberflächenkomponenten implementieren, die erforderlich sind, Formatierungsvorgänge zu machen für den Benutzer.  
  
 `CRichEditView` verwaltet das Text\- und Formatierungseigenschaft des Texts bei.  `CRichEditDoc` führt die Liste von Clientelementen, die in der Ansicht sind.  `CRichEditCntrItem` ContainerSeite bietet Zugriff auf die OLE\-Clientelementen.  
  
 Dieses allgemeine Windows\-Steuerelement \(und daher [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und die zugehörigen Klassen\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT\-Versionen 3,51 und höher ausgeführt werden.  
  
 Ein Beispiel für die Verwendung eines umfangreichen Bearbeitungsdokuments in einer MFC\-Anwendung, finden Sie die [WORDPAD](../../top/visual-cpp-samples.md) Beispielanwendung.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## Anforderungen  
 **Header:**  afxrich.h  
  
## Siehe auch  
 [MFC\-Beispiel WORDPAD](../../top/visual-cpp-samples.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem Class](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl Class](../../mfc/reference/cricheditctrl-class.md)