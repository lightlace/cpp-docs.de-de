---
title: "Drag &amp; Drop (OLE) | Microsoft Docs"
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
  - "Drag & Drop [C++]"
  - "Drag & Drop [C++], Informationen über Drag & Drop (OLE)"
  - "Drag & Drop-Unterstützung (Datei-Manager)"
  - "OLE-Anwendungen, Drag & Drop"
  - "Drag & Drop (OLE)"
  - "OLE-Serveranwendungen, Drag & Drop"
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Drag &amp; Drop (OLE)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Drag & Drop\-Funktion von OLE ist hauptsächlich eine Verknüpfung für das Kopieren und Einfügen von Daten.  Wenn Sie die Zwischenablage verwenden, um Daten zu kopieren oder einzufügen, sind mehrere Schritte erforderlich.  Sie wählen die Daten aus, klicken auf **Ausschneiden** oder **Kopieren** im Menü **Bearbeiten**, von der Verschiebung zur Zieldatei, im Fenster oder Anwendung, fügen den Cursor im gewünschten Speicherort und klicken im Menü **Bearbeiten** auf **Einfügen**.  
  
 Drag & Drop mit dem Datei\-Manager\-Drag& Drop\-Mechanismus unterschiedlich, der Dateinamen nur behandelt werden kann und speziell entworfen wurde, um Dateinamen auf Anwendungen zu übergeben.  Drag & Drop sind weitaus gebräuchlicher.  Er ermöglicht Ihnen die Drag & Drop\-Datenbindung alle Daten zu, die in der Zwischenablage auch platziert werden können.  
  
 Wenn Sie Drag & Drop verwenden, entfernen Sie zwei Schritte des Prozesses.  Sie wählen die Daten im Quellcodefenster die Ablagequelle \(""\), ziehen es an die gewünschte Ziel das Ablageziel \(""\) und löschen sie aus, indem Sie die Maustaste loslassen.  Der Vorgang entfällt die Notwendigkeit für Menüs und schneller ist als die Kopie\/die Pastensequenz.  Die einzige Anforderung ist, dass die Quelle und das Ablageziel statt dem Bildschirm geöffnet und zumindest teilweise sichtbar sein müssen.  
  
 Verwenden von Drag & Drop können Daten von einer Position zu anderen in einem Dokument, zwischen verschiedenen Dokumenten oder zwischen Anwendungen übertragen werden.  Es kann in einem Container oder in einer Serveranwendung, und alle Anwendungen kann eine Quelle, ein Ablageziel sein oder beides implementiert werden.  Wenn eine Anwendung, die die Quelle und Ablagezielhat Unterstützung implementiert werden, wird die Drag & Drop zwischen untergeordneten Fenstern oder innerhalb eines Fensters aktiviert.  Diese Funktion kann Ihre Anwendung deutlich einfacher stellen zu verwenden.  
  
 Wenn Sie nur die Drag & Drop\-Funktionen von OLE verwenden möchten, finden Sie unter [Drag & Drop: Anpassen](../mfc/drag-and-drop-customizing.md).  Sie können die Techniken verwenden, die in diesem Artikel erklärt werden, um Ablagequellen der Anwendungen vornehmen NichtOLE.  Der Artikel [Drag & Drop: Implementieren eines Ablageziels](../mfc/drag-and-drop-implementing-a-drop-target.md) beschreibt, wie Ablagezielunterstützung für Anwendungen und OLE NichtOLE implementiert.  Es ist auch hilfreich, die Beispiele [OCLIENT](../top/visual-cpp-samples.md) und [HIERSVR](../top/visual-cpp-samples.md) zu überprüfen MFC\-OLE.  
  
 Wenn Sie nicht die [Datenobjekte und Datenquellen \(OLE\)](../mfc/data-objects-and-data-sources-ole.md) Familie von Artikeln gelesen haben, sollten Sie dies jetzt tun.  Diese Artikel werden die Grundlagen der Datenübertragung und wie sie in Anwendungen implementiert.  
  
 Weitere Informationen über Drag & Drop, finden Sie unter:  
  
-   [Drag & Drop: Implementieren einer Quelle](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [Drag & Drop: Implementieren eines Ablageziels](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Drag & Drop: Anpassen](../mfc/drag-and-drop-customizing.md)  
  
## Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [Datenobjekte und Datenquellen \(OLE\)](../mfc/data-objects-and-data-sources-ole.md)