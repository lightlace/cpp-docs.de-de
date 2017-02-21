---
title: "Arbeiten mit Fensterobjekten | Microsoft Docs"
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
  - "Untergeordnete Fenster, Arbeiten mit"
  - "Fensterobjekte, Arbeiten mit"
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Arbeiten mit Fensterobjekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Arbeiten mit Fensteraufrufen für zwei Arten von Aktivitäten:  
  
-   Behandlungs\-Windows\-Meldungen  
  
-   Zeichnen im Fenster  
  
 Um Windows\-Meldungen in jedem Fenster, einschließlich der eigenen untergeordneten Fenster verarbeiten, finden Sie unter [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md) um die Meldungen in der C\+\+\-Fensterklasse zuzuordnen.  Schreiben Sie dann Meldungshandlermemberfunktionen in der Klasse.  
  
 Die meisten in einer Zeichnung Framework\-Anwendung wird in der Ansicht auf, deren [OnDraw](../Topic/CView::OnDraw.md)\-Memberfunktion aufgerufen wird, wenn der Inhalt des Fensters gezeichnet werden muss.  Wenn das Fenster ein untergeordnetes Element der Ansicht ist, Sie delegierte möglicherweise einen Teil der Zeichnungen der Ansicht hinweg im untergeordneten Fenster indem Sie `OnDraw` einen Aufruf der Memberfunktionen des Fensters verfügen.  
  
 In jedem Fall müssen Sie einen Gerätekontext zum Zeichnen.  Sie können die vordefinierten Stift, Pinseln und anderen Grafikobjekte verwenden, die im Gerätekontext enthalten werden, der dem Fenster zugeordnet ist.  Oder Sie können diese Objekte ändern, um die Zeichnungseffekte abzurufen, die Sie benötigen.  Wenn das Gerätekontext als Sie installiert ist, wie Sie, rufen Sie Memberfunktionen der [CDC](../mfc/reference/cdc-class.md) \(Gerätekontextklasse\) Linien, zu Formularen und dem Text auf; zu Farben verwenden; und einem Koordinatensystem arbeiten.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)  
  
-   [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)  
  
-   [Gerätekontexte](../mfc/device-contexts.md)  
  
-   [Grafikobjekte](../mfc/graphic-objects.md)  
  
## Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)