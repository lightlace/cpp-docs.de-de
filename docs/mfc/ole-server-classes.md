---
title: "OLE-Serverklasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM-Komponenten, Klassen"
  - "Komponentenklassen"
  - "OLE-Serveranwendungen, Serverklassen"
  - "OLE-Serverdokumente"
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# OLE-Serverklasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klassen werden durch Serveranwendungen verwendet.  Serverdokumente werden von `COleServerDoc` anstelle von **CDocument** abgeleitet.  Beachten Sie, dass, da `COleServerDoc` von `COleLinkingDoc` abgeleitet wird, Serverdokumente Container auch sein können, die das Verknüpfen unterstützen.  
  
 Die `COleServerItem`\-Klasse stellt ein Dokument oder einen Teil eines Dokuments an, das in einem anderen Dokument eingebettet oder verknüpft werden kann.  
  
 `COleIPFrameWnd` und `COleResizeBar` unterstützen direkte Bearbeiten, während das Objekt in einem Container und `COleTemplateServer` is Entwicklung der Dokument\/Ansicht zuordnen, sodass OLE\-Objekte von anderen Anwendungen bearbeitet werden können.  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Wird als Basisklasse für Serveranwendungsdokumentklassen.  `COleServerDoc`\-Objekte bieten der Hauptteil der Serverunterstützung von Interaktionen mit `COleServerItem`\-Objekten.  Visuelle Bearbeitungsfunktion wird mithilfe der Dokument\-\/Ansichtarchitektur der Klassenbibliothek bereitgestellt.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Abstrakte Basisklasse von `COleClientItem` und `COleServerItem`.  Objekte von Klassen, die von `CDocItem` abgeleitet sind, stellen Dokumente Teile dar.  
  
 [COleServerItem](../mfc/reference/coleserveritem-class.md)  
 Wird verwendet, um die OLE\-Schnittstelle zu `COleServerDoc`\-Elementen darzustellen.  Dies weist normalerweise ein `COleServerDoc`\-Objekt, das den eingebetteten Teil eines Dokuments darstellt.  In den Servern, die Links zu den Teilen Dokumenten, vorhanden sein können viele `COleServerItem`\-Objekte, von denen jedes einen Link zu einem Teil des Dokuments darstellt.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Stellt das Rahmenfenster für eine Ansicht bereit, wenn ein Serverdokument direkt bearbeitet wird.  
  
 [COleResizeBar](../mfc/reference/coleresizebar-class.md)  
 Stellt die Standardbenutzeroberfläche für direkte Größenanpassung bereit.  Objekte dieser Klasse sind immer in Verbindung mit `COleIPFrameWnd`\-Objekte.  
  
 [COleTemplateServer](../mfc/reference/coletemplateserver-class.md)  
 Wird verwendet, um Dokumente mit Dokument\-\/Ansichtarchitektur des Frameworks zu erstellen.  Delegaten `COleTemplateServer` eines Objekts höchst der Arbeit zu einem verknüpften `CDocTemplate`\-Objekt.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Eine Ausnahme, erstellten aus einem Fehler beim OLE\-Verarbeiten.  Diese Klasse wird von Container und Server verwendet.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)