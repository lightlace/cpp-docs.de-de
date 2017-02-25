---
title: "Dokumentklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.document"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dokumentklassen"
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Dokumentklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Dokumentklassenobjekte, erstellt durch Dokumentvorlagenobjekte, verwalten die Daten der Anwendung.  Sie leiten eine Klasse für Ihre Dokumente einer dieser Klassen.  
  
 Dokumentklassenobjekte interagieren mit Ansichtsobjekte.  Ansichtsobjekte stellen den Clientbereich eines Fensters dar, die Daten eines Dokuments an und ermöglichen Benutzern, um damit zu interagieren.  Dokumente und Ansichten werden durch ein Dokumentvorlagenobjekt erstellt.  
  
 [CDocument](../mfc/reference/cdocument-class.md)  
 Die Basisklasse für anwendungsspezifische Dokumente.  Leiten Sie die Dokumentklasse oder Klassen aus **CDocument**.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Wird für Verbunddokumentimplementierung sowie grundlegende Containerunterstützung.  Dient als Container für Klassen berechneten von [CDocItem](../mfc/reference/cdocitem-class.md).  Diese Klasse kann als Basisklasse für Containerdokumente verwendet werden und ist die Basisklasse für `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 Eine von `COleDocument` abgeleiteten Klasse, die die Infrastruktur für das Verknüpfen bereitstellt.  Sie sollten die Dokumentklassen für die Containeranwendungen dieser Klasse von `COleDocument` ableiten, wenn Sie sie an Links zu eingebetteten Objekten soll.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Führt die Liste der OLE\-Clientelementen, die im Rich\-Edit\-Steuerelement sind.  Wird mit [CRichEditView](../mfc/reference/cricheditview-class.md) und [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Wird als Basisklasse für Serveranwendungsdokumentklassen.  `COleServerDoc`\-Objekte bieten der Hauptteil der Serverunterstützung von Interaktionen mit [COleServerItem](../mfc/reference/coleserveritem-class.md)\-Objekten.  Visuelle Bearbeitungsfunktion wird mithilfe der Dokument\-\/Ansichtarchitektur der Klassenbibliothek bereitgestellt.  
  
 [CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)  
 Stellt, mit [CHtmlEditView](../mfc/reference/chtmleditview-class.md), die Funktionalität der Bearbeitungsplattform des web browser HTML im Kontext der MFC\-Dokument\-\/Ansichtarchitektur.  
  
## Verwandte Klassen  
 Dokumentklassenobjekte können dauerhaft sein \- das bedeutet, dass sie den Zustand an ein Speichermedium schreiben und lesen Sie es.  MFC stellt die `CArchive`\-Klasse, um die Daten, des Dokuments an ein Speichermedium zu übertragen zu erleichtern.  
  
 [CArchive](../mfc/reference/carchive-class.md)  
 Arbeitet mit einem [Die C\-Datei](../mfc/reference/cfile-class.md)\-Objekt zum Werkzeugpersistenten speicher für Objekte durch Serialisierung zusammen \(siehe [CObject::Serialize](../Topic/CObject::Serialize.md)\).  
  
 Dokumente können OLE\-Objekte auch enthalten.  `CDocItem` ist die Basisklasse der Server\- und Clientelemente.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Abstrakte Basisklasse von [COleClientItem](../mfc/reference/coleclientitem-class.md) und [COleServerItem](../mfc/reference/coleserveritem-class.md).  Objekte von Klassen, die von `CDocItem` abgeleitet sind, stellen Dokumente Teile dar.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)