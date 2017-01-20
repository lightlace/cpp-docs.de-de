---
title: "Verwalten von Daten mit Dokumentdatenvariablen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++], Friend"
  - "Auflistungsklassen [C++], verwendet von Dokumentobjekt"
  - "Daten [MFC]"
  - "Daten [MFC], Dokumente"
  - "Dokumentdaten [C++]"
  - "Dokumente [C++], Datenspeicher"
  - "friend-Klassen"
  - "Membervariablen [C++], Dokumentklasse"
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwalten von Daten mit Dokumentdatenvariablen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implementieren Sie die Daten des Dokuments als Membervariablen der Dokumentklasse.  deklariert beispielsweise das Scribbleprogramm einen Datenmember des `CObList`\-Typs eine verknüpfte Liste, die Zeiger auf `CObject`\-Objekten speichert.  Diese Liste wird verwendet, um Punktarrays zu speichern, die eine freihändige Strichzeichnung bilden.  
  
 Die Implementierung, hängen Memberdaten des Dokuments von der Art Ihrer Anwendung ab.  Um Ihnen, MFC\-Zubehör ein Gruppe "Auflistungsklassen" \- Arrays, Listen und Hybridwörterbücher \(Zuordnungen\), z Auflistungen auf Grundlage C\+\+\-Vorlagen \- zusammen mit Klassen out helfen, die eine Reihe von gängigen Datentypen wie `CString`, `CRect`, `CPoint`, `CSize` und `CTime` kapseln.  Weitere Informationen über diese Klassen, finden Sie unter [Klassenbibliotheks\-Übersicht](../mfc/class-library-overview.md) in der *MFC\-Referenz*.  
  
 Wenn Sie Memberdaten des Dokuments definiert haben, fügen Sie normalerweise Memberfunktionen der Dokumentklasse hinzu, um Datenelemente festzulegen und abzurufen und andere nützliche Vorgänge mit ihnen auszuführen.  
  
 Die Ansichten greifen auf das Dokumentobjekt zu, indem der Zeiger der Ansicht zum Dokument verwenden, installiert in der Ansicht zur Erstellungszeit.  Sie können diesen Zeiger in Memberfunktionen einer Ansicht abrufen, indem Sie die `CView`\-Memberfunktion **GetDocument** aufrufen.  Stellen Sie sicher, diesen Zeiger zu Ihren eigenen Dokumenttyp umzuwandeln.  Anschließend können Sie Member des amtlichen Dokuments durch den Zeiger verweisen.  
  
 Wenn häufige Datenübertragung Zugriff benötigt oder Sie die nicht öffentlichen Member der Dokumentklasse verwenden möchten, sollten Sie die Ansichtsklasse den Friend \(in C\+\+\-Begriffen\) von der Dokumentklasse machen.  
  
## Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)