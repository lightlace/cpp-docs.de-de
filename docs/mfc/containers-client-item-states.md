---
title: "Container: Client-Element-Zust&#228;nde"
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
  - "Clientelemente und OLE-Container"
  - "Lebensdauer, Lebenszeitzustände und OLE-Containerclientelemente"
  - "OLE-Container, Clientelement-Zustände"
  - "Zustände, OLE-Containerclientelement"
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Container: Client-Element-Zust&#228;nde
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die verschiedenen Zustände, die ein Clientelement von während seiner Lebensdauer wird.  
  
 Ein Clientelement wird durch mehrere Zustände, das erstellt, aktiviert, geändert und gespeichert ist.  Jedes Mal wenn die Statusänderungen des Elements, dem Framework [COleClientItem::OnChange](../Topic/COleClientItem::OnChange.md) mit der `OLE_CHANGED_STATE` aufruft Benachrichtigung.  Der zweite Parameter ist ein Wert der **COleClientItem::ItemState**\-Enumeration.  Er kann einen der folgenden Werte:  
  
-   **COleClientItem::emptyState**  
  
-   **COleClientItem::loadedState**  
  
-   **COleClientItem::openState**  
  
-   **COleClientItem::activeState**  
  
-   **COleClientItem::activeUIState**  
  
 im leeren Zustand ein Clientelement noch nicht vollständig ein Element.  Arbeitsspeicher ist dafür verbunden, aber noch nicht mit den Daten des OLE\-Elements initialisiert.  Dies ist der Zustand, den einem Clientelement ist in, wenn es durch einen Aufruf von **neu** erstellt wurde jedoch noch den zweiten Schritt der üblichen zwei Schritte umfassenden Erstellung unterzogen hat.  
  
 Im zweiten Schritt ausgeführt durch einen Aufruf von `COleClientItem::CreateFromFile` oder einer anderen Funktion **CreateFrom***xxxx*, wird das Element vollständig erstellt.  Die OLE\-Daten \(von einer Datei oder einer anderen Quelle, z der Zwischenablage sind\) mit `COleClientItem` abgeleitetes Objekt verbunden.  Jetzt wird das Element im geladenen Zustand.  
  
 Wenn ein Element im Fenster des Servers anstelle direkt im Dokument des Containers geöffnet geöffnet wurde, ist es im geöffneten \(vollständig oder öffnen Sie sie\), Zustand.  In diesem Zustand wird ein Kreuzschraffieren normalerweise über die Darstellung des Elements im Fenster des Containers gezeichnete, um anzugeben, dass das Element an anderer Stelle aktiv ist.  
  
 Wenn ein Element an der Stelle aktiviert wurde, übergibt es, normalerweise nur kurz, durch den aktiven Zustand.  Es gibt den aktiven Zustand der Benutzeroberfläche, in dem der Server die Menüs, Symbolleisten und andere Benutzeroberflächekomponenten mit denen des Containers zusammengeführt wurde.  Das Vorhandensein dieser Benutzeroberflächekomponenten unterscheidet den aktiven Zustand der Benutzeroberfläche im aktiven Zustand.  Andernfalls entspricht der aktiven Zustand dem aktiven Zustand der Benutzeroberfläche.  Wenn die Serverunterstützung rückgängig macht, muss der Server erforderlich, die Rückgängigzustandsinformationen des OLE\-Elements beizubehalten, nachdem sie geladen oder Zustand erreicht wird.  
  
## Siehe auch  
 [Container](../mfc/containers.md)   
 [Aktivierung](../mfc/activation-cpp.md)   
 [Container: Client\-Element\-Benachrichtigungen](../mfc/containers-client-item-notifications.md)   
 [Tracker](../mfc/trackers.md)   
 [CRectTracker Class](../mfc/reference/crecttracker-class.md)