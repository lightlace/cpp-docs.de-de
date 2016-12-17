---
title: "COleDocObjectItem Class"
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
  - "COleDocObjectItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDocObjectItem class"
  - "containment"
  - "containment, doc object"
  - "doc object containment"
  - "document object containment"
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# COleDocObjectItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Werkzeug\-Active Document\-Einschluss.  
  
## Syntax  
  
```  
class COleDocObjectItem : public COleClientItem  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDocObjectItem::COleDocObjectItem](../Topic/COleDocObjectItem::COleDocObjectItem.md)|Erstellt ein `COleDocObject`\-Element.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleDocObjectItem::DoDefaultPrinting](../Topic/COleDocObjectItem::DoDefaultPrinting.md)|Druckt das Dokument der Containeranwendung mit Einstellungen des standardmäßigen Druckers.|  
|[COleDocObjectItem::ExecCommand](../Topic/COleDocObjectItem::ExecCommand.md)|Führt den Befehl aus, der vom Benutzer angegeben wird.|  
|[COleDocObjectItem::GetActiveView](../Topic/COleDocObjectItem::GetActiveView.md)|Ruft die aktive Ansicht des Dokuments ab.|  
|[COleDocObjectItem::GetPageCount](../Topic/COleDocObjectItem::GetPageCount.md)|Ruft die Anzahl vonseiten im Dokument der Containeranwendung ab.|  
|[COleDocObjectItem::OnPreparePrinting](../Topic/COleDocObjectItem::OnPreparePrinting.md)|Erstellt das Dokument der Containeranwendung für das Drucken.|  
|[COleDocObjectItem::OnPrint](../Topic/COleDocObjectItem::OnPrint.md)|Druckt das Dokument der Containeranwendung.|  
|[COleDocObjectItem::QueryCommand](../Topic/COleDocObjectItem::QueryCommand.md)|Abfragen für den Status einer oder mehrerer Befehle generiert durch Benutzeroberflächenereignisse.|  
|[COleDocObjectItem::Release](../Topic/COleDocObjectItem::Release.md)|Gibt die Verbindung mit einem OLE verknüpften Element frei und schließt sie, wenn sie geöffnet wurde.  Zerstört nicht das Clientelement.|  
  
## Hinweise  
 In MFC wird ein aktives Dokument ähnlich wie in einer regulären, direkte Einbetten bearbeitbaren, mit den folgenden Unterschiede bearbeitet:  
  
-   `COleDocument` von abgeleitete Klasse führt noch eine Liste der momentan eingebetteten Elemente; Allerdings sind diese Elemente `COleDocObjectItem` von abgeleitete Elemente.  
  
-   Wenn ein aktives Dokument aktiv ist, nimmt sie den gesamten Clientbereich der Ansicht, wenn es direkt aktiviert ist.  
  
-   Ein Active Document\-Container hat die Steuerung des **Hilfe** Menüs.  
  
-   Das Menü enthält **Hilfe** Menüelemente für den Active Document\-Container und Server.  
  
 Da der Active Document\-Container das Menü **Hilfe** besitzt, ist der Container für das Weiterleiten von **Help**\-Servermenümeldungen an den Server verantwortlich.  Diese Integration wird durch `COleDocObjectItem` behandelt.  
  
 Weitere Informationen über das Zusammenführen von Menüs und aktive Dokumentenaktivierung, finden Sie in der Übersicht von [Active Document\-Einschluss](../../mfc/active-document-containment.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `COleDocObjectItem`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC Sampling MFCBIND](../../top/visual-cpp-samples.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [CDocObjectServerItem Class](../../mfc/reference/cdocobjectserveritem-class.md)