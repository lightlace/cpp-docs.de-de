---
title: "Aktivierung: Verben | Microsoft Docs"
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
  - "Aktivierung [C++], Verben"
  - "edit-Verb"
  - "OLE [C++], Aktivierung"
  - "OLE [C++], Bearbeiten"
  - "OLE-Aktivierung"
  - "Primäres Verb"
  - "Verben"
ms.assetid: eb56ff23-1de8-43ad-abeb-dc7346ba7b70
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Aktivierung: Verben
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die Rolle, die primäre und sekundäre Verben in OLE [Aktivierung](../mfc/activation-cpp.md) wiedergeben.  
  
 Normalerweise lässt das Doppelklicken auf ein eingebettetes Element dem Benutzer, um es zu bearbeiten.  Allerdings verhalten sich bestimmte Elemente auf diese Weise nicht.  Beispielsweise wird durch Doppelklicken auf ein Element, das mit der Anwendung der Sound Aufzeichnung erstellt wird, Server nicht in einem separaten Fenster; Stattdessen gibt sie den Sound wieder.  
  
 Der Grund für diesen Verhaltensunterschied ist, dass Elemente der Sound Aufzeichnung haben ein anderes "primäres Verb." Das primäre Verb ist die ausgeführte Aktion, wenn der Benutzer auf ein OLE\-Element doppelklickt.  Für die meisten Typen OLE\-Elemente, ist das wichtigste Verb Bearbeiten, die den Server startet, der das Element erstellt wurde.  Bei einigen Arten Elemente, z Elemente der Sound Aufzeichnung, ist das wichtigste Verb Spiel.  
  
 Viele Typen OLE\-Elemente unterstützen nur ein Verb, und Bearbeiten ist das häufigste.  Sowohl eine Elementtypen mehrere Verben.  Beispielsweise Elementunterstützungsbearbeitung der Sound Aufzeichnung als sekundäres Verb.  
  
 Ein weiteres Verb, das häufig verwendet wird, wird geöffnet.  Die geöffnete Verb steht zur Bearbeitung identisch, außer die Serveranwendung in einem separaten Fenster gestartet wird.  Dies Verb sollte verwendet werden, wenn entweder die Containeranwendung oder die Serveranwendung keine direkte Aktivierung unterstützt.  
  
 Alle Verben als primäres Verb müssen durch einen Untermenübefehl aufgerufen werden, wenn das Element ausgewählt ist.  Dies Untermenü enthält alle Verben, die vom Element unterstützt werden und nach den *Typnamen* Befehl  **Objekt** im Menü **Bearbeiten** erreicht.  Informationen zum den *Typnamen* **Objekt** Befehl, finden Sie im Artikel [Menüs und Ressourcen: Container\-Hinzufügungen](../mfc/menus-and-resources-container-additions.md).  
  
 Die Verben, die eine Serveranwendung unterstützt, werden in der Windows\-Registrierungsdatenbank aufgeführt.  Wenn die Serveranwendung mit der Microsoft Foundation Class\-Bibliothek geschrieben wird, registriert diese automatisch alle Verben, wenn der Server gestartet wird.  Wenn nicht, sollten Sie sie während der Initialisierungsphase der Serveranwendung registrieren.  Weitere Informationen finden Sie im Artikel [Registrierung](../mfc/registration.md).  
  
## Siehe auch  
 [Aktivierung](../mfc/activation-cpp.md)   
 [Container](../mfc/containers.md)   
 [Server](../mfc/servers.md)