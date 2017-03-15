---
title: "Bearbeiten von Bildlisten | Microsoft Docs"
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
  - "CImageList-Klasse, Bearbeiten"
  - "Bilderlisten [C++], Bearbeiten"
  - "Listen [C++], Bild"
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Bearbeiten von Bildlisten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Memberfunktion [Ersetzen](../Topic/CImageList::Replace.md) ersetzt ein Bild in einer Bildliste \([CImageList](../mfc/reference/cimagelist-class.md)\) durch ein neues Bild.  Diese Funktion ist auch nützlich, wenn Sie die Anzahl von Bildern in einem Bildlistenobjekt dynamisch erweitern müssen.  Die [SetImageCount](../Topic/CImageList::SetImageCount.md)\-Funktion ändert sich dynamisch die Anzahl von Bildern, die in der Bildliste gespeichert werden.  Wenn Sie die Größe der Bildliste erhöhen, Aufruf **Ersetzen** , um mit Bildern den neuen Bildslots hinzuzufügen.  Wenn Sie die Größe der Bildliste verringern, werden die Bilder zu der neuen Größe hinaus freigegeben.  
  
 Die Memberfunktion [Entfernen](../Topic/CImageList::Remove.md) entfernt ein Bild aus einer Bildliste.  Die [Kopieren](../Topic/CImageList::Copy.md)\-Memberfunktion kann innerhalb einer Bildliste Bilder kopieren oder umkehren.  Diese Funktion ermöglicht Ihnen, festzulegen, ob das Quellbild den Zielindex kopiert werden soll, oder die Quell\- und Zielbilder ausgetauscht werden sollen.  
  
 Um eine neue Bildliste indem Sie zwei Bildlisten zusammenführen zu erstellen, verwenden Sie die entsprechende Überladung der Memberfunktion [Erstellen](../Topic/CImageList::Create.md).  Diese Überladung von **Erstellen** wird das erste Bild der vorhandenen Bildlisten zusammen und speichert die daraus resultierende Anwendung in einem neuen Bildlistenobjekt.  Das neue Bild wird erstellt, indem transparent das zweite Bild über dem ersten zeichnet.  Die Maske für das neue Bild ist das Ergebnis dargestellt einer logischen OR\-Operation auf den Teilen der Masken für die zwei vorhandenen Bilder.  
  
 Dadurch wird überprüft, bis alle Bilder zum neuen Bildlistenobjekt zusammengeführt und hinzugefügt.  
  
 Sie können die einem Archiv Bildinformationen zu schreiben, indem Sie die Memberfunktion [Schreiben](../Topic/CImageList::Write.md) aufrufen, und lesen Sie es, indem Sie die Memberfunktion [Lesen](../Topic/CImageList::Read.md) aufrufen.  
  
 [GetSafeHandle](../Topic/CImageList::GetSafeHandle.md), [Anfügen](../Topic/CImageList::Attach.md) und [Trennen](../Topic/CImageList::Detach.md) können Sie Memberfunktionen, um das Handle die Bildliste zu bearbeiten, die dem `CImageList`\-Objekt angefügt, während die Memberfunktion [DeleteImageList](../Topic/CImageList::DeleteImageList.md) die Bildliste löschen, ohne das `CImageList`\-Objekt zu zerstören.  
  
## Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)