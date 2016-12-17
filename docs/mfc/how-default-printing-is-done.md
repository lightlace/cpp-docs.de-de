---
title: "Funktionsweise des Standarddrucks"
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
  - "Standarddruck"
  - "Standardwerte, Drucken"
  - "Drucken [MFC], Standard"
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Funktionsweise des Standarddrucks
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt den Standarddruckvorgang in Windows im Hinblick auf das MFC\-Framework.  
  
 In MFC\-Anwendungen hat die Ansichtsklasse eine Memberfunktion, die `OnDraw`, die den gesamten Zeichnungscode enthält.  `OnDraw` enthält einen Zeiger auf ein [CDC](../mfc/reference/cdc-class.md)\-Objekt als Parameter.  Diese `CDC`\-Objekt den Gerätekontext darstellt, um das Bild zu empfangen, generierten durch `OnDraw`.  Wenn das Fenster, das das Dokument angezeigt werden, eine [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Meldung empfängt, ruft das Framework `OnDraw` auf und übergibt es ein Gerätekontext für den Bildschirm ein [CPaintDC](../mfc/reference/cpaintdc-class.md) \(Objekt, spezifisch sein\).  Gemäß geht `OnDraw` Ausgabe dem Bildschirm.  
  
 In der Programmierung für Windows, ist das Senden ausgegeben zum Drucker zum Senden der Ausgabe in den Bildschirm sehr ähnlich.  Dies liegt daran, dass das Windows Graphics Device Interface \(GDI\) Hardware\-unabhängig ist.  Sie können die gleichen GDI\-Funktionen für Bildschirmanzeige oder für einfach Drucken verwenden, indem Sie den entsprechenden Gerätekontext verwenden.  Wenn das `CDC`\-Objekt, das einen `OnDraw` empfängt, den Drucker darstellt, geht `OnDraw` Ausgabe an den Drucker.  
  
 Dies ist, wie MFC\-Anwendungen einfachen Drucken ausführen können, ohne zusätzlichen Aufwand Ihrerseits zu erfordern.  Das Framework kümmert sich um Anzeigen des Druckdialogfeldfelds und Erstellen eines Gerätekontexts für den Drucker.  Wenn der Benutzer einen Druckbefehl der Menü Datei auswählt, wird die Ansicht den Gerätekontext von `OnDraw`, der das Dokument auf dem Drucker.  
  
 jedoch, gibt es mehrere wesentliche Unterschiede zwischen Drucken und Bildschirmanzeige.  Wenn von Druck\-, Sie das Dokument in unterschiedliche Seiten unterteilen und diese einzeln anzeigen müssen, anstatt zeigen Sie an, wie Rahmen in einem Fenster angezeigt wird.  Als Folge logische müssen Sie die Größe des Papiers berücksichtigen \(ob es Buchstabengröße, B4 oder ein Umschlag ist\).  Sie sollten in verschiedenen Ausrichtungen, wie Querformatmodus oder Hochformat drucken.  Die Microsoft Foundation Class\-Bibliothek kann nicht vorhergesagt, wie die Anwendung diese Probleme behandelt, daher stellt sie ein Protokoll bereit, damit Sie diese Funktionen hinzu.  
  
 Dieses Protokoll wird im Artikel [mehrseitige Dokumente](../mfc/multipage-documents.md) beschrieben.  
  
## Siehe auch  
 [Drucken](../mfc/printing.md)