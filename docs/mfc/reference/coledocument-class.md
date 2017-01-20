---
title: "COleDocument Class"
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
  - "COleDocument"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDocument class"
  - "Dokumente, OLE"
  - "OLE containers, client items"
  - "OLE-Dokumente"
  - "OLE-Dokumente, Basisklasse"
  - "visual editing, OLE document base class"
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# COleDocument Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse für OLE\-Dokumente, die visuelle Bearbeitung unterstützen.  
  
## Syntax  
  
```  
class COleDocument : public CDocument  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDocument::COleDocument](../Topic/COleDocument::COleDocument.md)|Erstellt ein `COleDocument`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleDocument::AddItem](../Topic/COleDocument::AddItem.md)|Fügt ein Element der Liste von Elementen hinzu, die durch das Dokument verwaltet werden.|  
|[COleDocument::ApplyPrintDevice](../Topic/COleDocument::ApplyPrintDevice.md)|Legt das DruckZiel Gerät für alle Clientelemente im Dokument fest.|  
|[COleDocument::EnableCompoundFile](../Topic/COleDocument::EnableCompoundFile.md)|Veranlasst Dokumente, mithilfe des OLE strukturierten Speicherdateiformats gespeichert.|  
|[COleDocument::GetInPlaceActiveItem](../Topic/COleDocument::GetInPlaceActiveItem.md)|Gibt das OLE\-Element zurück, das derzeit direkt aktiviert ist.|  
|[COleDocument::GetNextClientItem](../Topic/COleDocument::GetNextClientItem.md)|Ruft die nächste Clientelement zum Durchlaufen ab.|  
|[COleDocument::GetNextItem](../Topic/COleDocument::GetNextItem.md)|Ruft die nächste Dokumentelement zum Durchlaufen ab.|  
|[COleDocument::GetNextServerItem](../Topic/COleDocument::GetNextServerItem.md)|Ruft das folgende Serverelement zum Durchlaufen ab.|  
|[COleDocument::GetPrimarySelectedItem](../Topic/COleDocument::GetPrimarySelectedItem.md)|Gibt das primäre ausgewählte OLE\-Element im Dokument zurück.|  
|[COleDocument::GetStartPosition](../Topic/COleDocument::GetStartPosition.md)|Ruft die Startposition ab, Iteration zu starten.|  
|[COleDocument::HasBlankItems](../Topic/COleDocument::HasBlankItems.md)|Überprüfungen für leere Elemente im Dokument.|  
|[COleDocument::OnShowViews](../Topic/COleDocument::OnShowViews.md)|Aufgerufen, wenn das Dokument sichtbar oder nicht sichtbar ist.|  
|[COleDocument::RemoveItem](../Topic/COleDocument::RemoveItem.md)|Entfernt ein Element aus der Liste von Elementen, die durch das Dokument verwaltet werden.|  
|[COleDocument::UpdateModifiedFlag](../Topic/COleDocument::UpdateModifiedFlag.md)|Markiert das Dokument als geändert, wenn eines der enthaltenden OLE\-Elementen geändert wurden.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleDocument::OnEditChangeIcon](../Topic/COleDocument::OnEditChangeIcon.md)|Behandelt Ereignisse im Änderungs\-Symbolmenübefehl.|  
|[COleDocument::OnEditConvert](../Topic/COleDocument::OnEditConvert.md)|Behandelt die Konvertierung von eingebettet oder einem verknüpften Objekt von einem Typ in einen anderen.|  
|[COleDocument::OnEditLinks](../Topic/COleDocument::OnEditLinks.md)|Ereignisse in den Links Befehl im Menü Bearbeiten.|  
|[COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)|Sendet eine E\-Mail\-Nachricht mit dem angefügten Dokument.|  
|[COleDocument::OnUpdateEditChangeIcon](../Topic/COleDocument::OnUpdateEditChangeIcon.md)|Aufgerufen vom Framework, um die Befehlsbenutzeroberfläche für Bearbeiten\/die Änderungs\-Symbolmenüoption zu aktualisieren.|  
|[COleDocument::OnUpdateEditLinksMenu](../Topic/COleDocument::OnUpdateEditLinksMenu.md)|Aufgerufen vom Framework, um die Befehlsbenutzeroberfläche für die Bearbeiten\-\/Linkmenüoption zu aktualisieren.|  
|[COleDocument::OnUpdateObjectVerbMenu](../Topic/COleDocument::OnUpdateObjectVerbMenu.md)|Aufgerufen vom Framework, um die Befehlsbenutzeroberfläche für die Bearbeiten\-\/*ObjectName\-Menüoption* und das Verbuntermenü aktualisieren zugegriffen von Bearbeiten\/*Objektname*.|  
|[COleDocument::OnUpdatePasteLinkMenu](../Topic/COleDocument::OnUpdatePasteLinkMenu.md)|Aufgerufen vom Framework, um die Befehlsbenutzeroberfläche für die Inhalte einfügen\-Menüoption zu aktualisieren.|  
|[COleDocument::OnUpdatePasteMenu](../Topic/COleDocument::OnUpdatePasteMenu.md)|Aufgerufen vom Framework, um die Befehlsbenutzeroberfläche für die Pastenmenüoption zu aktualisieren.|  
  
## Hinweise  
 `COleDocument` wird von **CDocument** berechnet, das die OLE\-Anwendungen ermöglicht, die Dokument\-\/Ansichtarchitektur zu verwenden, die von Microsoft Foundation Class\-Bibliothek bereitgestellt wird.  
  
 `COleDocument` behandelt ein Dokument als Auflistung [CDocItem](../../mfc/reference/cdocitem-class.md)\-Objekte zu Handle OLE\-Elementen.  erfordern Container und Serveranwendungen eine solche Architektur, da ihre Dokumente in der Lage sein müssen, OLE\-Elemente zu enthalten.  Die [COleServerItem](../../mfc/reference/coleserveritem-class.md) und [COleClientItem](../../mfc/reference/coleclientitem-class.md)\-Klassen, beide, die von `CDocItem` abgeleitet werden, verwalten die Interaktionen zwischen Anwendungen und OLE\-Elementen.  
  
 Wenn Sie eine einfache Containeranwendung schreiben, leiten Sie die Dokumentklasse von `COleDocument`.  Wenn Sie eine Containeranwendung schreiben, die das Verknüpfen mit den eingebetteten Elemente unterstützt, die von ihrer Dokumente enthalten sind, leiten Sie die Dokumentklasse von [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md).  Wenn Sie einen Serveranwendungs\- oder Kombinationscontainer\/server schreiben, leiten Sie die Dokumentklasse von [COleServerDoc](../../mfc/reference/coleserverdoc-class.md).  `COleLinkingDoc` und `COleServerDoc` werden von `COleDocument` abgeleitet, sodass diese Klassen erben alle Dienste, die in `COleDocument` und in **CDocument** verfügbar sind.  
  
 Um `COleDocument` zu verwenden, leiten Sie eine Klasse davon und fügen Sie Funktionen hinzu um das NichtOLE\-die Daten der Anwendung sowie die eingebetteten oder verknüpfte Elemente zu verwalten.  Wenn Sie `CDocItem`\- die abgeleiteten Klassen definieren, um die systemeigene Daten der Anwendung zu speichern, können Sie die Standardimplementierung verwenden, die von `COleDocument` definiert wird, um Daten und OLE NichtOLE zu speichern.  Sie können eigene Datenstrukturen für Ihre Daten NichtOLE getrennt speichern auch entwerfen von den OLE\-Elementen.  Weitere Informationen finden Sie im Artikel [Container: Verbunddateien](../../mfc/containers-compound-files.md).  
  
 **CDocument** unterstützt das Senden des Dokuments über E\-Mail, wenn E\-Mail\-Unterstützung \(MAPI\) vorhanden ist.  `COleDocument` hat [OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md) aktualisiert, um Verbunddokumente ordnungsgemäß zu bearbeiten.  Weitere Informationen finden Sie in Artikel [MAPI](../../mfc/mapi.md) und [MAPI\-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC\-PROBENGEFÄSS](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel MFCBIND](../../top/visual-cpp-samples.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)