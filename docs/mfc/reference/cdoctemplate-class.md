---
title: "CDocTemplate Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocTemplate class"
  - "Dokumentvorlagen"
  - "Vorlagen, Dokument"
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine abstrakte Basisklasse, die die grundlegende Funktionalität für Dokumentvorlagen definiert.  
  
## Syntax  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDocTemplate::CDocTemplate](../Topic/CDocTemplate::CDocTemplate.md)|Erstellt ein `CDocTemplate`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDocTemplate::AddDocument](../Topic/CDocTemplate::AddDocument.md)|Fügt ein Dokument einer Vorlage hinzu.|  
|[CDocTemplate::CloseAllDocuments](../Topic/CDocTemplate::CloseAllDocuments.md)|Schließt alle Dokumente, die dieser Vorlage zugeordnet sind.|  
|[CDocTemplate::CreateNewDocument](../Topic/CDocTemplate::CreateNewDocument.md)|Erstellt ein neues Dokument.|  
|[CDocTemplate::CreateNewFrame](../Topic/CDocTemplate::CreateNewFrame.md)|Stellt ein neues Rahmenfenster erstellt, das ein Dokument und eine Ansicht enthält.|  
|[CDocTemplate::CreateOleFrame](../Topic/CDocTemplate::CreateOleFrame.md)|Stellt ein OLE\-aktiviertes Rahmenfenster erstellt.|  
|[CDocTemplate::CreatePreviewFrame](../Topic/CDocTemplate::CreatePreviewFrame.md)|Erstellt untergeordneter Frame, die für Reich\-Vorschau verwendet werden.|  
|[CDocTemplate::GetDocString](../Topic/CDocTemplate::GetDocString.md)|Ruft eine Zeichenfolge ab, die dem Dokumenttyp zugeordnet ist.|  
|[CDocTemplate::GetFirstDocPosition](../Topic/CDocTemplate::GetFirstDocPosition.md)|Ruft die Position des ersten Dokuments ab, das dieser Vorlage zugeordnet ist.|  
|[CDocTemplate::GetNextDoc](../Topic/CDocTemplate::GetNextDoc.md)|Ruft ein Dokument und die Position der folgenden ab.|  
|[CDocTemplate::InitialUpdateFrame](../Topic/CDocTemplate::InitialUpdateFrame.md)|Initialisiert das Rahmenfenster, und macht es optional sichtbar.|  
|[CDocTemplate::LoadTemplate](../Topic/CDocTemplate::LoadTemplate.md)|Lädt die Ressourcen von angegebenen `CDocTemplate` oder eine abgeleitete Klasse.|  
|[CDocTemplate::MatchDocType](../Topic/CDocTemplate::MatchDocType.md)|Bestimmt den Grad des Abhängigkeit in der Übereinstimmung zwischen einem Dokumenttyp und dieser Vorlage.|  
|[CDocTemplate::OpenDocumentFile](../Topic/CDocTemplate::OpenDocumentFile.md)|Öffnet eine Datei, die durch einen Pfadnamen angegeben wird.|  
|[CDocTemplate::RemoveDocument](../Topic/CDocTemplate::RemoveDocument.md)|Entfernt ein Dokument aus einer Vorlage.|  
|[CDocTemplate::SaveAllModified](../Topic/CDocTemplate::SaveAllModified.md)|Speichert alle Dokumente, die dieser Vorlage zugeordnet werden, die geändert wurden.|  
|[CDocTemplate::SetContainerInfo](../Topic/CDocTemplate::SetContainerInfo.md)|Bestimmt die Ressourcen für OLE\-Container, wenn, direktes Bearbeiten von OLE\-Element.|  
|[CDocTemplate::SetDefaultTitle](../Topic/CDocTemplate::SetDefaultTitle.md)|Zeigt den standardmäßigen Namen in der Titelleiste des Dokumentfensters an.|  
|[CDocTemplate::SetPreviewInfo](../Topic/CDocTemplate::SetPreviewInfo.md)|richtet aus Prozessvorschauhandler heraus.|  
|[CDocTemplate::SetServerInfo](../Topic/CDocTemplate::SetServerInfo.md)|Bestimmt die Ressourcen und Klassen, wenn das Serverdokument oder bearbeitetes direkt eingebettet ist.|  
  
## Hinweise  
 Sie erstellen gewöhnlich eine oder mehrere Dokumentvorlagen in der Implementierung von `InitInstance`\-Funktion der Anwendung.  Eine Normal\-Vorlage definiert die Beziehungen zwischen drei Typen Klassen:  
  
-   Eine Dokumentklasse, die Sie von **CDocument** berechnen.  
  
-   Eine Ansichtsklasse, die Daten aus der Dokumentklasse anzeigt, lässt oben auf.  Sie können diese Klasse von `CView`, von `CScrollView`, von `CFormView` oder von `CEditView` berechnen.  \(Sie können `CEditView` auch direkt verwenden.\)  
  
-   Eine Rahmenfensterklasse, die die Ansicht enthält.  Eine SDI\-Anwendung \(Single\-Document Interface\) berechnen Sie diese Klasse von `CFrameWnd`.  Eine Anwendung \(Multiple Document Interface\) berechnen Sie diese Klasse von `CMDIChildWnd`.  Wenn Sie nicht erforderlich ist, um das Verhalten des Rahmenfensters anzupassen, können Sie `CFrameWnd` oder `CMDIChildWnd` direkt verwenden, ohne eine eigene Klasse zu berechnen.  
  
 Die Anwendung verfügt über eine Normal\-Vorlage für jeden Typ Dokument, den sie unterstützt.  Wenn die Anwendung beispielsweise Arbeitsblätter und Textdokumente unterstützt, kann die Anwendung beiden Dokumentvorlagenobjekte.  Jede Normal\-Vorlage ist zum Erstellen und Verwalten aller Dokumente seines Typs zuständig.  
  
 Die Normal\-Vorlage speichert Zeiger auf `CRuntimeClass`\-Objekten für das Dokument, die Ansicht und die Rahmenfensterklassen.  Diese `CRuntimeClass`\-Objekte angegeben werden, wenn eine Normal\-Vorlage erstellt.  
  
 Die Normal\-Vorlage enthält die ID der Ressourcen, die dem Dokumenttyp verwendet werden \(wie Menü, Symbol oder Zugriffstastentabellenressourcenn\).  Die Normal\-Vorlage verfügt auch über die Zeichenfolgen, die zusätzliche Informationen zu den Dokumenttyp enthalten.  Diese schließen den Namen des Dokumenttyps \(beispielsweise, "Arbeitsblatt"\) und der Dateierweiterung ein \(beispielsweise, ".xls"\).  Optional kann es andere Zeichenfolgen enthalten, die von der Benutzeroberfläche der Anwendung, von der Windows\-Datei\-Manager\- und Object Linking and Embedding\-\(OLE\) verwendet werden unterstützt.  
  
 Wenn die Anwendung ein OLE\-Container und\/oder der Server ist, definiert die Normal\-Vorlage auch die ID des, das während der direkten Aktivierung verwendet wird.  Wenn die Anwendung ein OLE\-Server ist, definiert die Normal\-Vorlage die ID der Symbolleiste und des, die während der direkten Aktivierung verwendet werden.  Sie geben diese zusätzlichen OLE an, indem Sie `SetContainerInfo` und `SetServerInfo` aufrufen.  
  
 Da `CDocTemplate` eine abstrakte Klasse ist, können Sie die \- Klasse nicht direkt verwenden.  Eine typische \- Anwendung verwendet ein zwei `CDocTemplate`\- die abgeleiteten Klassen, die von Microsoft Foundation Class\-Bibliothek bereitgestellt werden: `CSingleDocTemplate`, das SDI implementiert, und `CMultiDocTemplate`, das MDI implementiert.  Siehe diese Klassen zu Informationen über die Verwendung von Dokumentvorlagen.  
  
 Wenn die Anwendung ein Benutzeroberflächeparadigma erfordert, das zu SDI oder MDI grundlegend unterscheiden, können Sie die eigene Klasse von `CDocTemplate` berechnen.  
  
 Weitere Informationen zu `CDocTemplate`, finden Sie unter [Dokumentvorlagen und der Dokument\/Ansichts\-Erstellungs\-Prozess](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocTemplate`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSingleDocTemplate Class](../../mfc/reference/csingledoctemplate-class.md)   
 [CMultiDocTemplate Class](../../mfc/reference/cmultidoctemplate-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [CEditView Class](../../mfc/reference/ceditview-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)