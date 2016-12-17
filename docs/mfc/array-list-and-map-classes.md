---
title: "Array-, Listen- und Zuordnungsklassen"
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
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Arrays [C++], Klassen"
  - "Auflistungsklassen, Listen"
  - "Auflistungsklassen, Zuordnungen"
  - "Listenklassen"
  - "Zuordnungsklassen"
ms.assetid: 81a13a7f-0c2c-4efd-b6bb-b4e624a0743d
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Array-, Listen- und Zuordnungsklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für die Behandlung von Aggregaten von Daten, die Klassenbibliothek eine Gruppe Auflistungsklassen \- Arrays, Listen und \- Zuordnungen die eine Vielzahl des Objekts und der vordefinierten Typen enthalten.  Die Auflistungen sind dynamisch angepasst.  Diese Klassen können in jedes Programm verwendet werden, ob bereits geschriebenem für Windows oder.  Sie können allerdings zum Implementieren der Datenstrukturen geeignet, die die im Dokumentklassen Anwendungsframework definieren.  Sie können spezialisiertere Auflistungsklassen dieser bereit ableiten, oder Sie können nach die Vorlagenklassen erstellen.  Weitere Informationen zu diesen Vorgehensweisen, finden Sie im Artikel [Auflistungen](../mfc/collections.md).  Eine Liste der Vorlagenauflistungsklassen, finden Sie im Artikel [Vorlagenklassen für Arrays, Listen und Zuordnungen](../mfc/template-classes-for-arrays-lists-and-maps.md).  
  
 Arrays sind eindimensionale Datenstrukturen, die nacheinander im Arbeitsspeicher gespeichert werden.  Sie unterstützen sehr schnellen wahlfreien Zugriff, da die angezeigte Speicheradresse eines gegebenen Elements abgeleitet werden kann, indem den Index des Elements um die Größe eines Elements multipliziert und das Ergebnis der Basisadresse des Arrays hinzugefügt wird.  Die Arrays sind sehr aufwändig, wenn Sie Einsatzelemente im Array müssen, da das gesamte Array der im Element eingefügten verschoben werden muss, um für das einzufügende Element Platz zu schaffen.  Arrays können ggf. wachsen und verkleinern.  
  
 Listen sind, ähnlich den Arrays jedoch werden sehr unterschiedlich gespeichert.  Jedes Element in einer Liste enthält auch einen Zeiger zu den vorherigen und folgende Elemente an und macht es eine doppelt verknüpfte Liste.  Es ist sehr schnell, Elemente, da die Möglichkeit hinzuzufügen oder zu löschen daher nur verwenden, mehrere Zeiger zu ändern.  Allerdings kann eine Liste zu suchen kostenintensiv sein, als alle Suchläufe mit eines der Enden der Liste beginnen müssen.  
  
 Zuordnungen verknüpfen einen Schlüsselwert an einen Datenwert.  Beispielsweise könnte die Schlüssel einer Zuordnung eine Zeichenfolge und die Daten ein Zeiger in eine Liste sein.  Sie würden um die Zuordnung anfordern, um Sie den Mauszeiger zu geben, der einer bestimmten Zeichenfolge zugeordnet wurde.  Zuordnungssuchen sind schnell, da Speicherbelegungen für Hashtabellen Schlüsselsuchen verwenden.  Hinzufügen und Löschen ist auch schnell.  Zuordnungen sind Datenstrukturen mit anderen als zusätzliche Indizes häufig verwendet.  MFC verwendet eine spezielle Art von Zuordnung [Meldungszuordnung](../mfc/mapping-messages.md) aufgerufen, um die Windows\-Meldungen in einen Zeiger auf eine Handlerfunktion für diese Nachricht zuzuordnen.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)