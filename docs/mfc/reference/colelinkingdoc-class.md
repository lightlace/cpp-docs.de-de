---
title: "COleLinkingDoc Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleLinkingDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleLinkingDoc class"
  - "OLE containers, client items"
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleLinkingDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse für OLE\-Containerdokumente, die das Verknüpfen mit den eingebetteten Elementen unterstützen, enthalten sie.  
  
## Syntax  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleLinkingDoc::COleLinkingDoc](../Topic/COleLinkingDoc::COleLinkingDoc.md)|Erstellt ein `COleLinkingDoc`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleLinkingDoc::Register](../Topic/COleLinkingDoc::Register.md)|Registriert das Dokument mit den OLE\-Systemen\-DLL.|  
|[COleLinkingDoc::Revoke](../Topic/COleLinkingDoc::Revoke.md)|Widerruft die Registrierung des Dokuments.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](../Topic/COleLinkingDoc::OnFindEmbeddedItem.md)|Sucht das angegebene eingebettete Element.|  
|[COleLinkingDoc::OnGetLinkedItem](../Topic/COleLinkingDoc::OnGetLinkedItem.md)|Sucht das angegebene verknüpfte Element.|  
  
## Hinweise  
 Eine Containeranwendung, die das Verknüpfen mit eingebetteten Elementen unterstützt, wird aufgerufen Linkcontainer einen "." Die [OCLIENT](../../top/visual-cpp-samples.md) Beispielanwendung ist ein Beispiel eines Linkcontainers.  
  
 Wenn die Quelle eines verknüpften Elements ein eingebettetes Element in einem anderen Dokument ist, muss dieses enthaltende Dokument geladen werden, sodass das eingebettete Element bearbeitet werden kann.  Aus diesem Grund muss ein Linkcontainer in der Lage sein, durch eine andere Containeranwendung ausgelöst werden, wenn der Benutzer die Quelle eines verknüpften Elements bearbeiten möchte.  Die Anwendung muss die [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)\-Klasse verwenden, damit sie Dokumente erstellen kann, wenn sie programmgesteuert gestartet wird.  
  
 Um den Container einen Linkcontainer zu erstellen, leiten Sie die Dokumentklasse von `COleLinkingDoc` anstelle [COleDocument](../../mfc/reference/coledocument-class.md).  Wie bei jedem anderen OLE\-Container, müssen Sie die Klasse zum Speichern der systemeigenen Daten sowie eingebetteten oder verknüpfte Elemente der Anwendung entwerfen.  Sie müssen außerdem Datenstrukturen zum Speichern der systemeigene Daten entwerfen.  Wenn Sie `CDocItem` von abgeleitete Klasse für die systemeigenen Daten der Anwendung definieren, können Sie die Schnittstelle verwenden, die von `COleDocument` definiert wird, um die systemeigene Daten sowie die OLE\-Daten zu speichern.  
  
 Um die Anwendung zu ermöglichen durch einen anderen Container programmgesteuert gestartet werden, deklarieren Sie ein `COleTemplateServer`\-Objekt als Member von `CWinApp` der Anwendung von abgeleitete Klasse:  
  
 [!CODE [NVC_MFCOleContainer#23](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOleContainer#23)]  
  
 In der `InitInstance`\-Memberfunktion aus dem `CWinApp` von abgeleitete Klasse, erstellen Sie eine Normal\-Vorlage und geben Sie das `COleLinkingDoc` an von abgeleitete Klasse als die Dokumentklasse:  
  
 [!CODE [NVC_MFCOleContainer#24](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOleContainer#24)]  
  
 Schließen Sie das `COleTemplateServer`\-Objekt zu den Dokumentvorlagen, indem Sie die `ConnectTemplate`\-Memberfunktion des Objekts aufrufen, und registrieren Sie alle Klassenobjekte mit dem OLE\-System, indem Sie **COleTemplateServer::RegisterAll** aufrufen:  
  
 [!CODE [NVC_MFCOleContainer#25](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOleContainer#25)]  
  
 Ein Beispiel `CWinApp`\- Definition der abgeleiteten Klasse und `InitInstance`\-Funktion, finden OCLIENT.H und OCLIENT.CPP im MFC\-Beispiel [OCLIENT](../../top/visual-cpp-samples.md).  
  
 Weitere Informationen zur Verwendung von `COleLinkingDoc`, finden Sie in Artikel [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md) und [Container: Erweiterte Funktionen](../../mfc/containers-advanced-features.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC\-Beispiel OCLIENT](../../top/visual-cpp-samples.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)