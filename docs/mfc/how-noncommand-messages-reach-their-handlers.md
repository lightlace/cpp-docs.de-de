---
title: "Wie nicht befehlsbasierte Meldungen ihre Handler erreichen"
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
  - "Meldungsbehandlung [C++], noncommand-Meldungen"
  - "Nachrichten [C++], Routing"
  - "noncommand-Meldungen"
  - "Windows-Nachrichten [C++], Routing"
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Wie nicht befehlsbasierte Meldungen ihre Handler erreichen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Anders als Befehle rufen Standardwindows\-meldungen nicht ab, weitergeleitet durch einen Instanzenweg Ziele sondern normalerweise vom Fenster behandelt, auf den sich Windows die Meldung sendet.  Das Fenster kann ein Hauptrahmenfenster, untergeordnetes MDI\-Fenster, ein Standardsteuerelement, ein Dialogfeld, eine Ansicht oder eine andere Art untergeordnetes Fenster.  
  
 Zur Laufzeit wird jedes Windows\-Fenster einem Window\-Objekt angefügt \(direkt oder indirekt von `CWnd` abgeleitet sind\) das seine eigene zugeordnete Meldungszuordnung und Handlerfunktionen hat.  Das Framework verwendet die Meldungszuordnung \- Sie für einen Befehl \- eingehenden Nachrichten an Handler zuzuordnen.  
  
## Siehe auch  
 [Wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md)