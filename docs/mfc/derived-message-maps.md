---
title: "Abgeleitete Meldungszuordnungen | Microsoft Docs"
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
  - "Abgeleitete Meldungszuordnungen"
  - "Meldungsbehandlung, Abgeleitete Meldungshandler"
  - "Meldungszuordnungen, Abgeleitet"
  - "Meldungen, Routing"
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Abgeleitete Meldungszuordnungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Während der Überprüfung die Meldungsbehandlung ist eigene Meldungszuordnung einer Klasse nicht das Ende der Meldungszuordnungsstorys.  Was geschieht, wenn `CMyView`\-Klasse \(abgeleitet von `CView`\) keinen entsprechenden Eintrag für eine Meldung verfügt?  
  
 Beachten Sie diese `CView`, die Basisklasse von `CMyView`, wird berechnet wiederum von `CWnd`.  Somit *ist*`CMyView` und `CView`*ist*`CWnd`.  Jede dieser Klassen verfügt über eine eigene Meldungszuordnung.  Die Abbildung "eine Ansichts\-Hierarchie" unten wird die hierarchische Beziehung der Klassen, aber erwähnt, dass ein `CMyView`\-Objekt ein einzelnes Objekt, das die Eigenschaften aller drei Klassen verfügt.  
  
 ![Ansichtshierarchie](../mfc/media/vc38621.png "vc38621")  
Eine Ansichts\-Hierarchie  
  
 Somit, wenn eine Meldung nicht in Klassen `CMyView` Meldungszuordnung gefunden wird, sucht das Framework auch die Meldungszuordnung seiner unmittelbaren Basisklasse.  Das Makro `BEGIN_MESSAGE_MAP` am Anfang der Meldungszuordnung gibt zwei Klassennamen als Argumente an:  
  
 [!CODE [NVC_MFCMessageHandling#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#2)]  
  
 Das erste Argument benennt die Klasse, die die Meldungszuordnung gehört.  Das zweite Argument stellt eine Verbindung mit der unmittelbaren Basisklasse \- `CView` hier \- sodass das Framework die Meldungszuordnung suchen, auch.  
  
 Die Meldungshandler, die in einer Basisklasse bereitgestellt werden, werden daher von der abgeleiteten Klasse geerbt.  Dies ist mit den normalen Memberfunktionen virtuellen sehr ähnlich, ohne zu erfordern, um alle Handlermemberfunktionen virtuell zu machen.  
  
 Wenn kein Handler in einem der Basisklassenmeldungszuordnungen gefunden wird, wird eine Standardverarbeitung der Meldung ausgeführt.  Wenn die Meldung ein Befehl ist, führt das Framework ihn folgendermaßen Befehlsziel weiter.  Wenn eine Standardwindows\-meldung ist, wird die Nachricht zur entsprechenden Standardfensterprozedur übergeben.  
  
 Um die folgenden übereinstimmenden Meldungszuordnung beschleunigen, speichert das Framework neue Übereinstimmungen auf der Wahrscheinlichkeit zwischen dass sie die gleiche Meldung erneut empfängt.  Dies hat zur Folge, dass das Framework nicht behandelte Nachrichten relativ effizient verarbeitet.  Meldungszuordnungen sind auch Leerzeichen\-effizienter als Implementierungen, die virtuellen Funktionen.  
  
## Siehe auch  
 [Wie das Framework Meldungszuordnungen durchsucht](../mfc/how-the-framework-searches-message-maps.md)