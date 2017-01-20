---
title: "COleServerDoc Class"
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
  - "COleServerDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleServerDoc class"
  - "container/server applications"
  - "OLE containers, server documents"
  - "OLE-Serveranwendungen, managing server documents"
  - "OLE server documents"
  - "server documents, OLE"
  - "Server, OLE"
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# COleServerDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse für OLE\-Serverdokumente.  
  
## Syntax  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleServerDoc::COleServerDoc](../Topic/COleServerDoc::COleServerDoc.md)|Erstellt ein `COleServerDoc`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleServerDoc::ActivateDocObject](../Topic/COleServerDoc::ActivateDocObject.md)|Ermöglicht das zugeordnete DocObject\-Dokument.|  
|[COleServerDoc::ActivateInPlace](../Topic/COleServerDoc::ActivateInPlace.md)|Ermöglicht das Dokument für die direkte Bearbeitung.|  
|[COleServerDoc::DeactivateAndUndo](../Topic/COleServerDoc::DeactivateAndUndo.md)|Deaktiviert die Benutzeroberfläche des Servers.|  
|[COleServerDoc::DiscardUndoState](../Topic/COleServerDoc::DiscardUndoState.md)|Verwirft Rückgängigzustandsinformationen.|  
|[COleServerDoc::GetClientSite](../Topic/COleServerDoc::GetClientSite.md)|Ruft einen Zeiger auf die zugrunde liegenden `IOleClientSite`\-Schnittstelle ab.|  
|[COleServerDoc::GetEmbeddedItem](../Topic/COleServerDoc::GetEmbeddedItem.md)|Gibt einen Zeiger auf ein Element zurück, das das gesamte Dokument darstellt.|  
|[COleServerDoc::GetItemClipRect](../Topic/COleServerDoc::GetItemClipRect.md)|Gibt das aktuelle Ausschneiderechteck für die direkte Bearbeitung zurück.|  
|[COleServerDoc::GetItemPosition](../Topic/COleServerDoc::GetItemPosition.md)|Gibt das Rechteck der aktuellen Position, relativ zum Clientbereich der Containeranwendung, für die direkte Bearbeitung zurück.|  
|[COleServerDoc::GetZoomFactor](../Topic/COleServerDoc::GetZoomFactor.md)|Gibt den Zoomfaktor in Pixel zurück.|  
|[COleServerDoc::IsDocObject](../Topic/COleServerDoc::IsDocObject.md)|Bestimmt, ob das Dokument ein DocObject ist.|  
|[COleServerDoc::IsEmbedded](../Topic/COleServerDoc::IsEmbedded.md)|Gibt an, ob das Dokument in einem Containerdokument oder in einem derzeit ausgeführten eingebettet ist, die eigenständig sind.|  
|[COleServerDoc::IsInPlaceActive](../Topic/COleServerDoc::IsInPlaceActive.md)|Gibt `TRUE` zurück, wenn das Element direkt an der Stelle aktiviert ist.|  
|[COleServerDoc::NotifyChanged](../Topic/COleServerDoc::NotifyChanged.md)|Benachrichtigt Container, dass der Benutzer das Dokument geändert hat.|  
|[COleServerDoc::NotifyClosed](../Topic/COleServerDoc::NotifyClosed.md)|Benachrichtigt Container, dass der Benutzer das Dokument geschlossen hat.|  
|[COleServerDoc::NotifyRename](../Topic/COleServerDoc::NotifyRename.md)|Benachrichtigt Container, dass der Benutzer das Dokument umbenannt wurde.|  
|[COleServerDoc::NotifySaved](../Topic/COleServerDoc::NotifySaved.md)|Benachrichtigt Container, dass der Benutzer das Dokument gespeichert hat.|  
|[COleServerDoc::OnDeactivate](../Topic/COleServerDoc::OnDeactivate.md)|Aufgerufen vom Framework, wenn der Benutzer ein Element deaktiviert, das an der Stelle aktiviert wurde.|  
|[COleServerDoc::OnDeactivateUI](../Topic/COleServerDoc::OnDeactivateUI.md)|Aufgerufen vom Framework, um die Steuerelemente und andere Elemente zu zerstören erstellt für direkte Aktivierung.|  
|[COleServerDoc::OnDocWindowActivate](../Topic/COleServerDoc::OnDocWindowActivate.md)|Aufgerufen vom Framework, wenn das Dokumentrahmenfenster des Containers aktiviert oder deaktiviert ist.|  
|[COleServerDoc::OnResizeBorder](../Topic/COleServerDoc::OnResizeBorder.md)|Aufgerufen vom Framework, wenn der das Rahmenfenster oder das Dokumentfenster Containeranwendung angepasst wird.|  
|[COleServerDoc::OnShowControlBars](../Topic/COleServerDoc::OnShowControlBars.md)|Aufgerufen durch das Framework, um Steuerleisten für die direkte Bearbeitung anzuzeigen oder auszublenden.|  
|[COleServerDoc::OnUpdateDocument](../Topic/COleServerDoc::OnUpdateDocument.md)|Aufgerufen vom Framework ausgelöst, wenn ein Serverdokument, das ein eingebettetes Element ist, gespeichert wird, die Kopie des Containers des Elements zu aktualisieren.|  
|[COleServerDoc::RequestPositionChange](../Topic/COleServerDoc::RequestPositionChange.md)|Ändert die Position der Rahmen der direkten Bearbeitung.|  
|[COleServerDoc::SaveEmbedding](../Topic/COleServerDoc::SaveEmbedding.md)|Teilt die Containeranwendung mit, das Dokument zu speichern.|  
|[COleServerDoc::ScrollContainerBy](../Topic/COleServerDoc::ScrollContainerBy.md)|Führt das Containerdokument aus.|  
|[COleServerDoc::UpdateAllItems](../Topic/COleServerDoc::UpdateAllItems.md)|Benachrichtigt Container, dass der Benutzer das Dokument geändert hat.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](../Topic/COleServerDoc::CreateInPlaceFrame.md)|Aufgerufen durch das Framework, um ein Rahmenfenster für die direkte Bearbeitung zu erstellen.|  
|[COleServerDoc::DestroyInPlaceFrame](../Topic/COleServerDoc::DestroyInPlaceFrame.md)|Aufgerufen durch das Framework, um ein Rahmenfenster für die direkte Bearbeitung zu zerstören.|  
|[COleServerDoc::GetDocObjectServer](../Topic/COleServerDoc::GetDocObjectServer.md)|Überschreiben Sie diese Funktion, um ein neues Objekt zu erstellen `CDocObjectServer` und anzugeben, dass dieses Dokument ein DocObject\-Container ist.|  
|[COleServerDoc::OnClose](../Topic/COleServerDoc::OnClose.md)|Aufgerufen vom Framework wenn Anforderungen eines Containers, das Dokument zu schließen.|  
|[COleServerDoc::OnExecOleCmd](../Topic/COleServerDoc::OnExecOleCmd.md)|Führt einen angegebenen Befehl aus, oder Anzeigen von für den Befehl.|  
|[COleServerDoc::OnFrameWindowActivate](../Topic/COleServerDoc::OnFrameWindowActivate.md)|Aufgerufen vom Framework, wenn das Rahmenfenster des Containers aktiviert oder deaktiviert ist.|  
|[COleServerDoc::OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md)|Aufgerufen, um `COleServerItem` abzurufen, das das gesamte Dokument darstellt; verwendet, um ein eingebettetes Element abzurufen.  Implementierung erforderlich.|  
|[COleServerDoc::OnReactivateAndUndo](../Topic/COleServerDoc::OnReactivateAndUndo.md)|Aufgerufen vom Framework, um die Änderungen rückgängig zu machen vorgenommen während der direkten Bearbeitung.|  
|[COleServerDoc::OnSetHostNames](../Topic/COleServerDoc::OnSetHostNames.md)|Aufgerufen vom Framework ausgelöst, wenn ein Container den Fenstertitel für ein eingebettetes Objekt festgelegt wird.|  
|[COleServerDoc::OnSetItemRects](../Topic/COleServerDoc::OnSetItemRects.md)|Aufgerufen vom Framework, um das Rahmenfenster der direkten Bearbeitung innerhalb des Fensters der Containeranwendung zu positionieren.|  
|[COleServerDoc::OnShowDocument](../Topic/COleServerDoc::OnShowDocument.md)|Aufgerufen vom Framework, um das Dokument anzuzeigen oder auszublenden.|  
  
## Hinweise  
 Ein Serverdokument kann [COleServerItem](../../mfc/reference/coleserveritem-class.md)\-Objekte enthalten, die die eingebetteten oder verknüpfte Elemente der Serverschnittstelle darstellen.  Wenn eine Serveranwendung durch einen Container, ein eingebettetes Element bearbeiten gestartet wird, wird das Element als sein eigenes Serverdokument geladen; das `COleServerDoc`\-Objekt enthält nur ein `COleServerItem`\-Objekt und besteht aus dem gesamten Dokument.  Wenn eine Serveranwendung durch einen Container, ein verknüpftes Element bearbeiten gestartet wird, wird ein vorhandenes Dokument vom Datenträger geladen; ein Teil des Inhalts des Dokuments wird hervorgehoben, um das verknüpfte Element anzugeben.  
  
 `COleServerDoc`\-Objekte können Elemente der [COleClientItem](../../mfc/reference/coleclientitem-class.md)\-Klasse auch enthalten.  Dies ermöglicht es Ihnen, ContainerServer Anwendungen zu erstellen.  Das Framework bietet Funktionen, um die `COleClientItem`\-Elemente, während `COleServerItem` Wartung ordnungsgemäß gespeichert werden.  
  
 Wenn die Serveranwendung nicht Links vornimmt, enthält ein Serverdokument immer nur ein Serverelement, das das gesamte eingebettete Objekt als Dokument darstellt.  Wenn die Serveranwendung Links vornimmt, muss sie ein Serverelement erstellen, wenn eine Auswahl in die Zwischenablage kopiert wird.  
  
 Um `COleServerDoc` zu verwenden, leiten Sie eine Klasse davon und implementieren Sie die [OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md)\-Memberfunktion, die den Server zu Unterstützung eingebetteten Elemente zulässig.  Leiten Sie eine Klasse von `COleServerItem`, um die Elemente in Dokumenten zu implementieren, und geben Sie Objekte dieser Klasse von `OnGetEmbeddedItem` zurück.  
  
 Zur Unterstützung verknüpfte Elemente, `COleServerDoc` bereitstellt [OnGetLinkedItem](../Topic/COleLinkingDoc::OnGetLinkedItem.md) die Memberfunktion.  Sie können die Standardimplementierung verwenden oder sie überschreiben, wenn Sie eine eigene Methode Verwaltung von Dokumentelementen haben.  
  
 Sie benötigen ein `COleServerDoc` von abgeleitete Klasse für jeden Typ Serverdokument die Anwendung unterstützt.  Wenn die Serveranwendung Arbeitsblätter und Diagramme unterstützt, benötigen Sie zwei `COleServerDoc` von abgeleitete Klassen.  
  
 Weitere Informationen zu Server, finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC\-Beispiel HIERSVR](../../top/visual-cpp-samples.md)   
 [COleLinkingDoc Class](../../mfc/reference/colelinkingdoc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [COleLinkingDoc Class](../../mfc/reference/colelinkingdoc-class.md)   
 [COleTemplateServer Class](../../mfc/reference/coletemplateserver-class.md)