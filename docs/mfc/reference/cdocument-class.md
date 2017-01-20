---
title: "CDocument Class"
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
  - "CDocument"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocument class"
  - "Befehlsbehandlung, documents and"
  - "Befehlsrouting, documents and"
  - "Dokumente [C++], Befehlsrouting"
  - "Dokumente [C++], document classes"
  - "Dokumente [C++], Mehrere Ansichten"
  - "Dokumente [C++], Serialisierung"
  - "Dateien [C++], Dokumente"
  - "Serialisierung [C++], documents and"
  - "Ansichten [C++], Dokument"
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CDocument Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die grundlegende Funktionalität für benutzerdefinierte Dokumentklassen bereit.  
  
## Syntax  
  
```  
class CDocument : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDocument::CDocument](../Topic/CDocument::CDocument.md)|Erstellt ein `CDocument`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDocument::AddView](../Topic/CDocument::AddView.md)|Fügt eine Ansicht an das Dokument an.|  
|[CDocument::BeginReadChunks](../Topic/CDocument::BeginReadChunks.md)|Initialisiert Blockslesen.|  
|[CDocument::CanCloseFrame](../Topic/CDocument::CanCloseFrame.md)|Erweitertes überschreibbares; aufgerufen, bevor ein Rahmenfenster geschlossen wird, das dieses Dokument anzeigt.|  
|[CDocument::ClearChunkList](../Topic/CDocument::ClearChunkList.md)|Löscht die Blocksliste.|  
|[CDocument::ClearPathName](../Topic/CDocument::ClearPathName.md)|Löscht den Pfad von dem Document\-Objekt frei.|  
|[CDocument::DeleteContents](../Topic/CDocument::DeleteContents.md)|Aufgerufen, um Bereinigung des Dokuments auszuführen.|  
|[CDocument::FindChunk](../Topic/CDocument::FindChunk.md)|Sucht nach einem Block mit dem angegebenen GUID.|  
|[CDocument::GetAdapter](../Topic/CDocument::GetAdapter.md)|Gibt einen Zeiger zurück, um aufzufüllen, `IDocument`\-Schnittstelle zu implementieren.|  
|[CDocument::GetDocTemplate](../Topic/CDocument::GetDocTemplate.md)|Gibt einen Zeiger auf die Normal\-Vorlage zurück, die den Typ des Dokuments beschreibt.|  
|[CDocument::GetFile](../Topic/CDocument::GetFile.md)|Gibt einen Zeiger auf den gewünschten `CFile`\-Objekt zurück.|  
|[CDocument::GetFirstViewPosition](../Topic/CDocument::GetFirstViewPosition.md)|Gibt die Position der ersten in der Liste der Ansichten zurück; verwendet, um Iteration zu starten.|  
|[CDocument::GetNextView](../Topic/CDocument::GetNextView.md)|Läuft durch die Liste Sichten durch, die dem Dokument zugeordnet werden.|  
|[CDocument::GetPathName](../Topic/CDocument::GetPathName.md)|Gibt den Pfad der Datendatei des Dokuments zurück.|  
|[CDocument::GetThumbnail](../Topic/CDocument::GetThumbnail.md)|Aufgerufen, um eine Miniaturansicht anzuzeigen, um vom Miniaturansichtsanbieter verwendet werden, Bitmap zu erstellen.|  
|[CDocument::GetTitle](../Topic/CDocument::GetTitle.md)|Gibt den Namen des Dokuments zurück.|  
|[CDocument::InitializeSearchContent](../Topic/CDocument::InitializeSearchContent.md)|Aufgerufen, um Sucheninhalt für Suchen\-Handler zu initialisieren.|  
|[CDocument::IsModified](../Topic/CDocument::IsModified.md)|Gibt an, ob das Dokument geändert wurde, seit er zuletzt gespeichert wurde.|  
|[CDocument::IsSearchAndOrganizeHandler](../Topic/CDocument::IsSearchAndOrganizeHandler.md)|Teilt mit, ob diese Instanz von `CDocument`\-Objekt für Suche erstellt &. Handler organisiert wurde.|  
|[CDocument::LoadDocumentFromStream](../Topic/CDocument::LoadDocumentFromStream.md)|Aufgerufen, um Dokumentendaten vom Stream verwenden.|  
|[CDocument::OnBeforeRichPreviewFontChanged](../Topic/CDocument::OnBeforeRichPreviewFontChanged.md)|Aufgerufen, bevor Reich\-Vorschauschriftart geändert wird.|  
|[CDocument::OnChangedViewList](../Topic/CDocument::OnChangedViewList.md)|Aufgerufen, nachdem eine Ansicht hinzugefügt ist oder aus dem Dokument entfernt.|  
|[CDocument::OnCloseDocument](../Topic/CDocument::OnCloseDocument.md)|Aufgerufen, um das Dokument zu schließen.|  
|[CDocument::OnCreatePreviewFrame](../Topic/CDocument::OnCreatePreviewFrame.md)|Aufgerufen vom Framework, wenn es Vorschauframe für Reich\-Vorschau erstellen.|  
|[CDocument::OnDocumentEvent](../Topic/CDocument::OnDocumentEvent.md)|Aufgerufen vom Framework als Reaktion auf ein Dokumentenereignis.|  
|[CDocument::OnDrawThumbnail](../Topic/CDocument::OnDrawThumbnail.md)|Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um Inhalt der Miniaturansicht zu zeichnen.|  
|[CDocument::OnLoadDocumentFromStream](../Topic/CDocument::OnLoadDocumentFromStream.md)|Aufgerufen vom Framework, wenn sie die Dokumentendaten vom Stream geladen werden muss.|  
|[CDocument::OnNewDocument](../Topic/CDocument::OnNewDocument.md)|Aufgerufen, um ein neues Dokument zu erstellen.|  
|[CDocument::OnOpenDocument](../Topic/CDocument::OnOpenDocument.md)|Aufgerufen, um ein vorhandenes Dokument zu öffnen.|  
|[CDocument::OnPreviewHandlerQueryFocus](../Topic/CDocument::OnPreviewHandlerQueryFocus.md)|Beauftragt den Vorschauhandler, HWND aus dem Aufrufen der GetFocus\-Funktion zurückzugeben.|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](../Topic/CDocument::OnPreviewHandlerTranslateAccelerator.md)|Beauftragt den Vorschauhandler, eine Tastatureingaben zu behandeln, die oben aus der Meldungsverteilschleife des Prozesses übergeben wird, in dem der Vorschauhandler ausgeführt wird.|  
|[CDocument::OnRichPreviewBackColorChanged](../Topic/CDocument::OnRichPreviewBackColorChanged.md)|Aufgerufen, wenn Reich\-Vorschauhintergrundfarbe geändert hat.|  
|[CDocument::OnRichPreviewFontChanged](../Topic/CDocument::OnRichPreviewFontChanged.md)|Aufgerufen, wenn Reich\-Vorschauschriftart geändert hat.|  
|[CDocument::OnRichPreviewSiteChanged](../Topic/CDocument::OnRichPreviewSiteChanged.md)|Aufgerufen, wenn Reich\-Vorschausite geändert hat.|  
|[CDocument::OnRichPreviewTextColorChanged](../Topic/CDocument::OnRichPreviewTextColorChanged.md)|Aufgerufen, wenn Reich\-Vorschautextfarbe geändert hat.|  
|[CDocument::OnSaveDocument](../Topic/CDocument::OnSaveDocument.md)|Aufgerufen, um das Dokument auf dem Datenträger zu speichern.|  
|[CDocument::OnUnloadHandler](../Topic/CDocument::OnUnloadHandler.md)|Aufgerufen vom Framework, wenn der Vorschauhandler entladen wird.|  
|[CDocument::PreCloseFrame](../Topic/CDocument::PreCloseFrame.md)|Aufgerufen vor dem Rahmenfenster wird geschlossen.|  
|[CDocument::ReadNextChunkValue](../Topic/CDocument::ReadNextChunkValue.md)|Liest folgenden Blockswert.|  
|[CDocument::ReleaseFile](../Topic/CDocument::ReleaseFile.md)|Gibt eine Datei auschecken, um sie bereitzustellen für andere Anwendungen.|  
|[CDocument::RemoveChunk](../Topic/CDocument::RemoveChunk.md)|Entfernt einen Block mit angegebenem GUID.|  
|[CDocument::RemoveView](../Topic/CDocument::RemoveView.md)|Trennt eine Ansicht im Dokument.|  
|[CDocument::ReportSaveLoadException](../Topic/CDocument::ReportSaveLoadException.md)|Erweitertes schreibbares; aufgerufen, wenn ein offenes oder ein Speichervorgang aufgrund einer Ausnahme abgeschlossen werden können.|  
|[CDocument::SaveModified](../Topic/CDocument::SaveModified.md)|Erweitertes schreibbares; aufgerufen, um den Benutzer zu fragen, ob das Dokument gespeichert werden soll.|  
|[CDocument::SetChunkValue](../Topic/CDocument::SetChunkValue.md)|Legt einen Blockswert fest.|  
|[CDocument::SetModifiedFlag](../Topic/CDocument::SetModifiedFlag.md)|Legt ein Flag fest, dass Sie das Dokument geändert haben, seit der zuletzt gespeichert wurde.|  
|[CDocument::SetPathName](../Topic/CDocument::SetPathName.md)|Legt den Pfad der Datendatei ab, die durch das Dokument verwendet wird.|  
|[CDocument::SetTitle](../Topic/CDocument::SetTitle.md)|Legt den Namen des Dokuments fest.|  
|[CDocument::UpdateAllViews](../Topic/CDocument::UpdateAllViews.md)|Benachrichtigt alle Ansichten, die Dokument geändert wurde.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDocument::OnFileSendMail](../Topic/CDocument::OnFileSendMail.md)|Sendet eine E\-Mail\-Nachricht mit dem angefügten Dokument.|  
|[CDocument::OnUpdateFileSendMail](../Topic/CDocument::OnUpdateFileSendMail.md)|Ermöglicht den sendens\-E\-Mail\-Befehl, wenn E\-Mail\-Unterstützung vorhanden ist.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDocument::m\_bGetThumbnailMode](../Topic/CDocument::m_bGetThumbnailMode.md)|Gibt an, dass `CDocument`\-Objekt durch dllhost für Miniaturansichten erstellt wurde.  sollte dieses in dem `CView::OnDraw`.|  
|[CDocument::m\_bPreviewHandlerMode](../Topic/CDocument::m_bPreviewHandlerMode.md)|Gibt an, dass `CDocument`\-Objekt durch prevhost für `Rich Preview` erstellt wurde.  sollte dieses in dem `CView::OnDraw`.|  
|[CDocument::m\_bSearchMode](../Topic/CDocument::m_bSearchMode.md)|Gibt an, dass `CDocument`\-Objekt dem Indexer oder anderer Suchen\-Anwendung erstellt wurde.|  
|[CDocument::m\_clrRichPreviewBackColor](../Topic/CDocument::m_clrRichPreviewBackColor.md)|Gibt Hintergrundfarbe des Reich\-Vorschaufensters an.  Diese Farbe wird von Host festgelegt.|  
|[CDocument::m\_clrRichPreviewTextColor](../Topic/CDocument::m_clrRichPreviewTextColor.md)|Gibt Vordergrundfarbe des Reich\-Vorschaufensters an.  Diese Farbe wird von Host festgelegt.|  
|[CDocument::m\_lfRichPreviewFont](../Topic/CDocument::m_lfRichPreviewFont.md)|Gibt Textschriftart für Reich\-Vorschaufenster an.  Diese Schriftartinformationen werden vom Host festgelegt.|  
  
## Hinweise  
 Ein Dokument stellt die Gruppierung von Daten dar, die der Benutzer in der Regel mit dem geöffneten Befehl der Datei geöffnet und mit dem Datei\-Abwehrbefehl gespeichert werden.  
  
 **CDocument** Standardvorgänge unterstützt das Erstellen eines Dokuments, das Laden und Speichern es.  Das Framework bearbeitet Dokumente mithilfe der Schnittstelle, die von **CDocument** definiert ist.  
  
 Eine Anwendung kann mehr als einen Typ Dokument unterstützen; beispielsweise unterstützt möglicherweise eine Anwendung Arbeitsblätter und Textdokumente.  Jeder Typ Dokument verfügt über eine zugeordnete Normal\-Vorlage; die Normal\-Vorlage gibt an, welche Ressourcen \(beispielsweise, Menü, Symbol oder Zugriffstastentabelle\) für diesen Typ des Dokuments verwendet werden.  Jedes Dokument enthält einen Zeiger auf dem zugeordneten `CDocTemplate`\-Objekt.  
  
 Benutzer interagieren mit einem Dokument unter [CView](../../mfc/reference/cview-class.md)\-Objekte, die zugeordnet.  Eine Ansicht rendert ein Bild des Dokuments in einem Rahmenfenster und interpretiert Benutzereingaben als Vorgänge im Dokument.  Ein Dokument kann mehrere Ansichten verfügen, die zugeordnet.  Wenn der Benutzer ein Fenster auf einem Dokument öffnet, erstellt das Framework eine Ansicht und fügt sie dem Dokument an.  Die Normal\-Vorlage gibt an, welcher Ansichts\- und Rahmenfenster verwendet werden, um jeden Typ Dokument anzuzeigen.  
  
 Dokumente sind Teil des Standardbefehlsroutings des Frameworks empfangen und infolgedessen Befehle von den Standardbenutzeroberflächenkomponenten \(wie dem Datei\-Abwehrmenüelement\).  Ein Dokument empfängt die Befehle, die durch die aktive Ansicht weitergeleitet werden.  Wenn das Dokument keinen angegebenen Befehl verarbeitet, wird es den Befehl an die Normal\-Vorlage weiter, die ihn verwaltet.  
  
 Wenn die Daten eines Dokuments geändert werden, muss jede seiner Ansichten diese Änderungen widerspiegeln.  **CDocument** stellt die [UpdateAllViews](../Topic/CDocument::UpdateAllViews.md)\-Memberfunktion bereit, sodass Sie die Ansichten solche Änderungen benachrichtigen, sodass die Ansichten nach Bedarf selbst neu zeichnet.  Das Framework benötigt auch den Benutzer auf, eine geänderte Datei zu speichern, bevor sie geschlossen wird.  
  
 Um Dokumente in einer typischen Anwendung implementieren, müssen Sie wie folgt vorgehen:  
  
-   Leiten Sie eine Klasse von **CDocument** für jeden Typ Dokument.  
  
-   Fügen Sie Membervariablen hinzu, um die Daten jedes Dokuments zu speichern.  
  
-   Implementieren Sie Memberfunktionen für das Lesen und Ändern der Daten des Dokuments.  Die Ansichten des Dokuments sind die wichtigsten Benutzer dieser Memberfunktionen.  
  
-   Überschreiben Sie die [CObject::Serialize](../Topic/CObject::Serialize.md)\-Memberfunktion der Dokumentklasse, um die Daten des Dokuments nach und von einem Datenträger zu schreiben und zu lesen.  
  
 **CDocument** unterstützt das Senden des Dokuments über E\-Mail, wenn E\-Mail\-Unterstützung \(MAPI\) vorhanden ist.  Siehe die Artikel [MAPI](../../mfc/mapi.md) und [MAPI\-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md).  
  
 Weitere Informationen zu **CDocument**, finden Sie unter [Serialisierung](../../mfc/serialization-in-mfc.md), [Dokument\-\/Ansichtsarchitektur\-Themen](../../mfc/document-view-architecture.md) und [Dokument\/Ansichts\-Erstellung](../../mfc/document-view-creation.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC überprüft MDIDOCVW](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel SNAPVW](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel\-NPP](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)