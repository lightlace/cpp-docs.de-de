---
title: "OLE-Containerklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Klassen [C++]"
  - "Containerklassen [C++]"
  - "Container [C++], OLE-Containeranwendungen"
  - "OLE [C++], Klassen"
  - "OLE-Klassen [C++]"
  - "Visuelle Bearbeitung [C++], Klassen"
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE-Containerklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klassen werden durch Containeranwendungen verwendet.  `COleLinkingDoc` und `COleDocument` verwalten Auflistungen `COleClientItem`\-Objekte.  Anstatt, die Dokumentklasse von **CDocument** die Ableitung, leiten Sie ihn von `COleLinkingDoc` oder `COleDocument`, je nachdem, ob Sie Unterstützung für Links zu Objekten benötigen, die im Dokument eingebettet sind.  
  
 Verwenden Sie ein `COleClientItem`\-Objekt, um jedes OLE\-Element im Dokument dargestellt, das von einem anderen Dokument eingebettet ist oder ein Link zu einem anderen Dokument ist.  
  
 [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)  
 Unterstützt Active Document\-Einschluss.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Wird für Verbunddokumentimplementierung sowie grundlegende Containerunterstützung.  Dient als Container für Klassen berechneten von `CDocItem`.  Diese Klasse kann als Basisklasse für Containerdokumente verwendet werden und ist die Basisklasse für `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 Eine von `COleDocument` abgeleiteten Klasse, die die Infrastruktur für das Verknüpfen bereitstellt.  Sie sollten die Dokumentklassen für die Containeranwendungen dieser Klasse von `COleDocument` ableiten, wenn Sie sie an Links zu eingebetteten Objekten soll.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Führt die Liste der OLE\-Clientelementen, die im Rich\-Edit\-Steuerelement sind.  Wird mit [CRichEditView](../mfc/reference/cricheditview-class.md) und [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Abstrakte Basisklasse von `COleClientItem` und `COleServerItem`.  Objekte von Klassen, die von `CDocItem` abgeleitet sind, stellen Dokumente Teile dar.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md)  
 Eine Clientelementklasse, die die Seite des Clients der Verbindung mit einem eingebetteten oder verknüpften OLE\-Element darstellt.  Ableiten der Clientelemente von dieser Klasse.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 Bietet clientseitigen Zugriff auf ein OLE\-Element, das in einem Rich\-Edit\-Steuerelement gespeichert wird, wenn Sie mit `CRichEditView` und `CRichEditDoc` verwendet werden.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Eine Ausnahme, erstellten aus einem Fehler beim OLE\-Verarbeiten.  Diese Klasse wird von Container und Server verwendet.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)