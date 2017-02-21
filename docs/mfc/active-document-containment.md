---
title: "Active Document-Container | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Active Document-Container [C++], Informationen über Active Document-Container"
  - "Aktive Dokumente [C++], Container"
  - "Container [C++], aktives Dokument"
  - "MFC [C++], COM-Unterstützung"
  - "MFC-COM [C++], Active Document-Einschluss"
ms.assetid: b8dfa74b-75ce-47df-b75e-fc87b7f7d687
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Active Document-Container
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Active Document\-Einschluss ist eine Technologie, die einzelnen Frames bietet, in denen, mit Dokumenten zu arbeiten, anstatt, Sie zu erzwingen, dass mehrere Anwendung zu erstellen und zu verwenden, wie für jeden Dokumenttyp.  Es unterscheidet sich der grundlegenden OLE\-Technologie in dieses OLE\-Arbeiten mit eingebetteten Objekten innerhalb eines Verbunddokuments, in dem nur ein einzelner des Inhalts aktiv sein kann.  Mit Active Document\-Einschluss aktivieren Sie ein vollständiges Dokument \(das heißt, eine komplette Anwendung, einschließlich zugeordneten Menüs, Symbolleisten, z.\) im Kontext einzelnen Frame.  
  
 Die Active Document\-Einschluss\-Technologie wurde ursprünglich entwickelt, sodass Microsoft Office sollte implementiert.  Allerdings stellt die Technologie flexibel genug, Active Document\-Container als sollte zu unterstützen und kann Dokumentserver als Office und Office kompatible Anwendungen unterstützen.  
  
 Die Anwendung, die Active Documents hostet, wird [Active Document\-Container](../mfc/active-document-containers.md) aufgerufen.  Beispiele für solche Container sind der Microsoft Office\-Binder oder Microsoft Internet Explorer.  
  
 Active Document\-Einschluss wird als Satz Erweiterungen zu OLE\-Dokumenten, die Verbunddokumenttechnologie von OLE implementiert.  Die Erweiterungen sind weitere Schnittstellen, die einem integrierbaren, direkten Objekt ermöglichen, ein ganzes Dokument anstelle eines Einzelstücks des eingebetteten Inhalt darzustellen.  Wie mit OLE\-Dokumenten, verwendet Active Document\-Einschluss einen Container, der den Platz hat für Active Documents bereitstellt, und Server, die die Benutzeroberfläche und Manipulationsfunktionen für aktive Dokumente selbst bereitstellen.  
  
 [Active Document\-Server](../mfc/active-document-servers.md) ist eine Anwendung \(z Word, Excel, PowerPoint oder\) diese Unterstützung eine oder mehrere Dokumentklassen aktiven, wobei jedes Objekt selbst die Erweiterungsschnittstellen unterstützt, die das in ermöglichen einen \- Container zu aktivierenden Objekt.  
  
 [aktives Dokument](../mfc/active-documents.md) \(bereitgestellt von einem Active Document\-Server wie Word oder Excel\) ist im Wesentlichen ein komplettes, konventionelles Dokument, das Objekt in einem anderen als Active Document\-Container eingebettet wird.  Anders als eingebettete Objekte haben Active Documents vollständige Kontrolle über den Seiten, und die gesamte Schnittstelle der Anwendung \(mit sämtlichen zugrunde liegenden Befehle und Tools\) ist verfügbar dem Benutzer, zu bearbeiten.  
  
 Ein aktives Dokument wird genau verstanden, indem sie von einem Standardole \- gebettet Element des Attributs unterscheidet.  Nach der OLE\-Konvention ist ein eingebettetes Objekt eines, das innerhalb der Seite des Dokuments angezeigt wird, das er besitzt, und das Dokument wird durch einen OLE\-Container verwaltet.  Der Container speichert Daten des eingebetteten Objekts mit dem Rest des Dokuments.  Allerdings werden eingebettete Objekte insofern beschränkt, dass sie nicht die Seite kontrollieren, auf der sie auftreten.  
  
 Benutzer einer Active Document\-Container\-Anwendung können die aktiven Dokumente \(bezeichnet Abschnitte im sollte\) mit ihrer Lieblings\-Anwendungen erstellen \(bereitgestellt diesen Anwendungen um das aktive Dokument aktiviert\), jedoch können die Benutzer das resultierende Projekt verwalten als einzelne Entität, die eindeutig benannt werden kann, gespeichert wurden, gedruckt, u. a.  Entsprechend kann ein Benutzer eines Internetbrowsers das gesamte Netzwerk und die lokalen Dateisysteme, als Speicherentität des Einzelbelegs mit der Fähigkeit behandeln, Dokumente in diesem Speicher von einem einzelnen Speicherort zu suchen.  
  
## Beispielprogramme  
  
-   [MFCBIND](../top/visual-cpp-samples.md) Das Beispiel veranschaulicht die Implementierung einer Active Document\-Container\-Anwendung.  
  
## Siehe auch  
 [MFC COM](../mfc/mfc-com.md)