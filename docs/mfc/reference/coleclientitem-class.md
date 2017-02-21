---
title: "COleClientItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleClientItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "client items and OLE containers"
  - "COleClientItem class"
  - "container interface class"
  - "OLE client item class"
  - "OLE containers, client items"
  - "OLE containers, interface class"
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleClientItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Definiert die Containerschnittstelle zu den OLE\-Elementen.  
  
## Syntax  
  
```  
class COleClientItem : public CDocItem  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleClientItem::COleClientItem](../Topic/COleClientItem::COleClientItem.md)|Erstellt ein `COleClientItem`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleClientItem::Activate](../Topic/COleClientItem::Activate.md)|Öffnet das OLE\-Element für einen Vorgang und dann das angegebene Verb aus.|  
|[COleClientItem::ActivateAs](../Topic/COleClientItem::ActivateAs.md)|Ermöglicht das Element als anderer Typ.|  
|[COleClientItem::AttachDataObject](../Topic/COleClientItem::AttachDataObject.md)|Greift auf die Daten im OLE\-Objekt zu.|  
|[COleClientItem::CanCreateFromData](../Topic/COleClientItem::CanCreateFromData.md)|Gibt an, ob eine Containeranwendung ein eingebettetes Objekt erstellen kann.|  
|[COleClientItem::CanCreateLinkFromData](../Topic/COleClientItem::CanCreateLinkFromData.md)|Gibt an, ob eine Containeranwendung ein verknüpftes Objekt erstellen kann.|  
|[COleClientItem::CanPaste](../Topic/COleClientItem::CanPaste.md)|Gibt an, ob die Zwischenablage ein integrierbares oder statische OLE\-Element enthält.|  
|[COleClientItem::CanPasteLink](../Topic/COleClientItem::CanPasteLink.md)|Gibt an, ob die Zwischenablage ein verbindbares OLE\-Element enthält.|  
|[COleClientItem::Close](../Topic/COleClientItem::Close.md)|Schließt, eine Verbindung zu einem Server jedoch zerstört nicht das OLE\-Element.|  
|[COleClientItem::ConvertTo](../Topic/COleClientItem::ConvertTo.md)|Konvertiert das Element zu einem anderen Typ.|  
|[COleClientItem::CopyToClipboard](../Topic/COleClientItem::CopyToClipboard.md)|Kopiert das OLE\-Element in die Zwischenablage.|  
|[COleClientItem::CreateCloneFrom](../Topic/COleClientItem::CreateCloneFrom.md)|Stellt ein Duplikat eines vorhandenen Elements erstellt.|  
|[COleClientItem::CreateFromClipboard](../Topic/COleClientItem::CreateFromClipboard.md)|Erstellt ein eingebettetes Element aus der Zwischenablage.|  
|[COleClientItem::CreateFromData](../Topic/COleClientItem::CreateFromData.md)|Erstellt ein eingebettetes Element aus einem Datenobjekt.|  
|[COleClientItem::CreateFromFile](../Topic/COleClientItem::CreateFromFile.md)|Erstellt ein eingebettetes Element aus einer Datei.|  
|[COleClientItem::CreateLinkFromClipboard](../Topic/COleClientItem::CreateLinkFromClipboard.md)|Erstellt ein verknüpftes Element aus der Zwischenablage.|  
|[COleClientItem::CreateLinkFromData](../Topic/COleClientItem::CreateLinkFromData.md)|Erstellt ein verknüpftes Element aus einem Datenobjekt.|  
|[COleClientItem::CreateLinkFromFile](../Topic/COleClientItem::CreateLinkFromFile.md)|Erstellt ein verknüpftes Element aus einer Datei.|  
|[COleClientItem::CreateNewItem](../Topic/COleClientItem::CreateNewItem.md)|Erstellt ein neues eingebettetes Element starten, indem die Serveranwendung.|  
|[COleClientItem::CreateStaticFromClipboard](../Topic/COleClientItem::CreateStaticFromClipboard.md)|Erstellt ein statisches Element aus der Zwischenablage.|  
|[COleClientItem::CreateStaticFromData](../Topic/COleClientItem::CreateStaticFromData.md)|Erstellt ein statisches Element aus einem Datenobjekt.|  
|[COleClientItem::Deactivate](../Topic/COleClientItem::Deactivate.md)|Deaktiviert das Element.|  
|[COleClientItem::DeactivateUI](../Topic/COleClientItem::DeactivateUI.md)|Stellt die Benutzeroberfläche der Containeranwendung in ihren ursprünglichen Zustand zurück.|  
|[COleClientItem::Delete](../Topic/COleClientItem::Delete.md)|Löscht oder schließt das OLE\-Element, wenn es ein verknüpftes Element war.|  
|[COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md)|Führt ein Drag & Drop\-Vorgang aus.|  
|[COleClientItem::DoVerb](../Topic/COleClientItem::DoVerb.md)|Führt das angegebene Verb aus.|  
|[COleClientItem::Draw](../Topic/COleClientItem::Draw.md)|Zeichnet das OLE\-Element.|  
|[COleClientItem::GetActiveView](../Topic/COleClientItem::GetActiveView.md)|Ruft die Ansicht ab, auf der das Element an der Stelle aktiviert ist.|  
|[COleClientItem::GetCachedExtent](../Topic/COleClientItem::GetCachedExtent.md)|Gibt die Grenzen des Rechtecks des OLE\-Elements zurück.|  
|[COleClientItem::GetClassID](../Topic/COleClientItem::GetClassID.md)|Ruft die ID Klasse des vorhandenen Elements ab|  
|[COleClientItem::GetClipboardData](../Topic/COleClientItem::GetClipboardData.md)|Ruft die Daten ab, die in der Zwischenablage gespeichert werden, indem die `CopyToClipboard`\-Memberfunktion aufgerufen wurde.|  
|[COleClientItem::GetDocument](../Topic/COleClientItem::GetDocument.md)|Gibt das `COleDocument`\-Objekt zurück, das das vorhandene Element enthält.|  
|[COleClientItem::GetDrawAspect](../Topic/COleClientItem::GetDrawAspect.md)|Ruft die aktuelle Ansicht des Elements zum Rendern ab.|  
|[COleClientItem::GetExtent](../Topic/COleClientItem::GetExtent.md)|Gibt die Grenzen des Rechtecks des OLE\-Elements zurück.|  
|[COleClientItem::GetIconFromRegistry](../Topic/COleClientItem::GetIconFromRegistry.md)|Retrives ein Handle für ein Symbol zugeordnet mit dem Server eines bestimmten CLSID.|  
|[COleClientItem::GetIconicMetafile](../Topic/COleClientItem::GetIconicMetafile.md)|Ruft die Metadatei ab, die für das Zeichnen des Symbols des Elements verwendet wird.|  
|[COleClientItem::GetInPlaceWindow](../Topic/COleClientItem::GetInPlaceWindow.md)|Gibt einen Zeiger auf das Fenster der direkten Bearbeitung des Elements.|  
|[COleClientItem::GetItemState](../Topic/COleClientItem::GetItemState.md)|Ruft den aktuellen Zustand des Elements ab.|  
|[COleClientItem::GetLastStatus](../Topic/COleClientItem::GetLastStatus.md)|Gibt den Status des Vorgangs des letzten OLE zurück.|  
|[COleClientItem::GetLinkUpdateOptions](../Topic/COleClientItem::GetLinkUpdateOptions.md)|Gibt den Updatemodus für ein verknüpftes Element zurück \(erweiterte Funktion\).|  
|[COleClientItem::GetType](../Topic/COleClientItem::GetType.md)|Gibt den Typ \(eingebettet, verknüpft oder statisch\) des OLE\-Elements zurück.|  
|[COleClientItem::GetUserType](../Topic/COleClientItem::GetUserType.md)|Ruft eine Zeichenfolge ab, die den Typ des Elements beschreibt.|  
|[COleClientItem::IsInPlaceActive](../Topic/COleClientItem::IsInPlaceActive.md)|Gibt `TRUE` zurück, wenn das Element direkt aktiviert ist.|  
|[COleClientItem::IsLinkUpToDate](../Topic/COleClientItem::IsLinkUpToDate.md)|Gibt **TRUE** zurück, wenn ein verknüpftes Element mit dem Quelldokument auf dem neuesten Stand ist.|  
|[COleClientItem::IsModified](../Topic/COleClientItem::IsModified.md)|Gibt `TRUE` zurück, wenn das Element geändert wurde, seit er zuletzt gespeichert wurde.|  
|[COleClientItem::IsOpen](../Topic/COleClientItem::IsOpen.md)|Gibt `TRUE` zurück, wenn das Element in der Serveranwendung geöffnet ist.|  
|[COleClientItem::IsRunning](../Topic/COleClientItem::IsRunning.md)|Gibt `TRUE` zurück, wenn die Serveranwendung des Elements ausgeführt wird.|  
|[COleClientItem::OnActivate](../Topic/COleClientItem::OnActivate.md)|Aufgerufen vom Framework, um das Element zu benachrichtigen, dass es aktiviert ist.|  
|[COleClientItem::OnActivateUI](../Topic/COleClientItem::OnActivateUI.md)|Aufgerufen vom Framework, um das Element zu benachrichtigen, dass es aktiviert ist und die Benutzeroberfläche anzeigen soll.|  
|[COleClientItem::OnChange](../Topic/COleClientItem::OnChange.md)|Aufgerufen, wenn der Server das OLE\-Element ändert.  Implementierung erforderlich.|  
|[COleClientItem::OnDeactivate](../Topic/COleClientItem::OnDeactivate.md)|Aufgerufen vom Framework ausgelöst, wenn ein Element deaktiviert wird.|  
|[COleClientItem::OnDeactivateUI](../Topic/COleClientItem::OnDeactivateUI.md)|Aufgerufen vom Framework, wenn der Server die direkte Benutzeroberfläche entfernt wurde.|  
|[COleClientItem::OnGetClipboardData](../Topic/COleClientItem::OnGetClipboardData.md)|Aufgerufen vom Framework, die in die Zwischenablage kopiert werden, Daten abzurufen.|  
|[COleClientItem::OnInsertMenus](../Topic/COleClientItem::OnInsertMenus.md)|Aufgerufen vom Framework, um ein zusammengesetztes Menü zu erstellen.|  
|[COleClientItem::OnRemoveMenus](../Topic/COleClientItem::OnRemoveMenus.md)|Aufgerufen durch das Framework, um die Menüs des Containers von einem zusammengesetzten Menü zu entfernen.|  
|[COleClientItem::OnSetMenu](../Topic/COleClientItem::OnSetMenu.md)|Aufgerufen vom Framework, um ein zusammengesetztes Menü zu installieren und zu entfernen.|  
|[COleClientItem::OnShowControlBars](../Topic/COleClientItem::OnShowControlBars.md)|Aufgerufen durch das Framework, um Steuerleisten ein\- und auszublenden.|  
|[COleClientItem::OnUpdateFrameTitle](../Topic/COleClientItem::OnUpdateFrameTitle.md)|Aufgerufen vom Framework, um die Titelleiste des Rahmenfensters zu aktualisieren.|  
|[COleClientItem::ReactivateAndUndo](../Topic/COleClientItem::ReactivateAndUndo.md)|Aktiviert das Element und macht den letzten Vorgang der direkten Bearbeitung.|  
|[COleClientItem::Release](../Topic/COleClientItem::Release.md)|Gibt die Verbindung mit einem OLE verknüpften Element frei und schließt sie, wenn sie geöffnet wurde.  Zerstört nicht das Clientelement.|  
|[COleClientItem::Reload](../Topic/COleClientItem::Reload.md)|Lädt das Element nach einem Aufruf von `ActivateAs` erneut.|  
|[COleClientItem::Run](../Topic/COleClientItem::Run.md)|Führt die Anwendung aus, die dem Element zugeordnet wird.|  
|[COleClientItem::SetDrawAspect](../Topic/COleClientItem::SetDrawAspect.md)|Legt die aktuelle Ansicht des Elements zum Rendern fest.|  
|[COleClientItem::SetExtent](../Topic/COleClientItem::SetExtent.md)|Legt das umschließende Rechteck des OLE\-Elements fest.|  
|[COleClientItem::SetHostNames](../Topic/COleClientItem::SetHostNames.md)|Legt die Namen fest, die der Server anzeigt, wenn er das OLE\-Element bearbeitet.|  
|[COleClientItem::SetIconicMetafile](../Topic/COleClientItem::SetIconicMetafile.md)|Zwischenspeichert die Metadatei, die für das Zeichnen des Symbols des Elements verwendet wird.|  
|[COleClientItem::SetItemRects](../Topic/COleClientItem::SetItemRects.md)|Legt das umschließende Rechteck des Elements fest.|  
|[COleClientItem::SetLinkUpdateOptions](../Topic/COleClientItem::SetLinkUpdateOptions.md)|Legt den Updatemodus für ein verknüpftes Element fest \(erweiterte Funktion\).|  
|[COleClientItem::SetPrintDevice](../Topic/COleClientItem::SetPrintDevice.md)|Legt das DruckZiel Gerät für dieses Clientelement fest.|  
|[COleClientItem::UpdateLink](../Topic/COleClientItem::UpdateLink.md)|Aktualisiert den Präsentationscachen eines Elements.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleClientItem::CanActivate](../Topic/COleClientItem::CanActivate.md)|Aufgerufen vom Framework, um zu bestimmen, ob direkte Aktivierung zulässig ist.|  
|[COleClientItem::OnChangeItemPosition](../Topic/COleClientItem::OnChangeItemPosition.md)|Aufgerufen vom Framework, wenn die Position eines Elements ändert.|  
|[COleClientItem::OnDeactivateAndUndo](../Topic/COleClientItem::OnDeactivateAndUndo.md)|Aufgerufen durch das Framework, um nach Aktivierung rückgängig zu machen.|  
|[COleClientItem::OnDiscardUndoState](../Topic/COleClientItem::OnDiscardUndoState.md)|Aufgerufen vom Framework, um die Rückgängigzustandsinformationen des Elements zu verwerfen.|  
|[COleClientItem::OnGetClipRect](../Topic/COleClientItem::OnGetClipRect.md)|Aufgerufen vom Framework, um die Ausschneiderechteckkoordinaten des Elements abzurufen.|  
|[COleClientItem::OnGetItemPosition](../Topic/COleClientItem::OnGetItemPosition.md)|Aufgerufen durch das Framework, um die Position des Elements relativ zur Ansicht abzurufen.|  
|[COleClientItem::OnGetWindowContext](../Topic/COleClientItem::OnGetWindowContext.md)|Aufgerufen vom Framework, wenn ein Element an der Stelle aktiviert ist.|  
|[COleClientItem::OnScrollBy](../Topic/COleClientItem::OnScrollBy.md)|Aufgerufen vom Framework, um das Element in einblenden.|  
|[COleClientItem::OnShowItem](../Topic/COleClientItem::OnShowItem.md)|Aufgerufen vom Framework, um das OLE\-Element anzuzeigen.|  
  
## Hinweise  
 Ein OLE\-Element stellt die Daten dar, erstellt und von einer Serveranwendung verwaltet, die in ein Dokument "nahtlos" enthalten sein können, damit sie für den Benutzer angezeigt wird, ein einzelnes Dokument zu sein.  Das Ergebnis ist ein "Verbunddokument", das vom OLE\-Element und von einem enthaltenden Dokument gebildet wird.  
  
 Ein OLE\-Element kann entweder eingebettet werden oder verknüpft sind.  Wenn es eingebettet ist, werden die Daten als Teil des Verbunddokuments gespeichert.  Wenn es verknüpft ist, werden die Daten als Teil einer separaten Datei gespeichert, die von der Serveranwendung erstellt wird, und nur ein Link zu dieser Datei wird im Verbunddokument gespeichert.  Alle OLE\-Elemente enthalten die Informationen, die die Serveranwendung angeben, die aufgerufen werden soll, um sie zu bearbeiten.  
  
 `COleClientItem` definiert mehrere überschreibbare Funktionen, die als Reaktion auf Anforderungen von der Serveranwendung aufgerufen werden; diese overridables treten normalerweise als Benachrichtigungen auf.  Dies ermöglicht die Serveranwendung, den Container zu Änderungen zu informieren, die der Benutzer führt, wenn das OLE\-Element bearbeitet, oder Informationen abzurufen, die während der Bearbeitung erforderlich sind.  
  
 `COleClientItem` kann mit der [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) oder [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)\-Klasse verwendet werden.  Um `COleClientItem` zu verwenden, leiten Sie eine Klasse davon und implementieren Sie die [OnChange](../Topic/COleClientItem::OnChange.md)\-Memberfunktion, die definiert wie der Container auf die Änderungen reagiert, die am Element vorgenommen werden.  Um direkte Aktivierung zu unterstützen, überschreiben Sie die [OnGetItemPosition](../Topic/COleClientItem::OnGetItemPosition.md)\-Memberfunktion.  Diese Funktion bietet Informationen über die angezeigte Position des OLE\-Elements.  
  
 Weitere Informationen zur Verwendung der Containerschnittstelle, finden Sie in Artikel [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md) und [Aktivierung](../../mfc/activation-cpp.md).  
  
> [!NOTE]
>  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] bezeichnet die eingebetteten und verknüpften Elemente als "Objekte" verweist auf Typen von Elementen als "Klassen" an. Dieser Verweis wird der Begriff "Element", um die OLE\-Entität vom entsprechenden C\+\+\-Objekt und dem Begriff "Typ" zu unterscheiden, um die OLE\-Kategorie von der C\+\+\-Klasse zu unterscheiden.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC\-Beispiel MFCBIND](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel OCLIENT](../../top/visual-cpp-samples.md)   
 [CDocItem Class](../../mfc/reference/cdocitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)