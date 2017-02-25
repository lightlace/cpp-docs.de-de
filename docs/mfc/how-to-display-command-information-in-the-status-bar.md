---
title: "Gewusst wie: Anzeigen von Befehlsinformationen in der Statusleiste | Microsoft Docs"
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
  - "Anzeigen des Befehlsstatus"
  - "Eingabeaufforderungen [C++]"
  - "Statusleisten, Anzeigen von Befehlsinformationen"
  - "Statusleisten, Meldungsbereich"
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Gewusst wie: Anzeigen von Befehlsinformationen in der Statusleiste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie im Anwendungs\-Assistenten ausführen, um das Skelett der Anwendung zu erstellen, können Sie eine Symbolleiste und eine Statusleiste unterstützen.  Derzeit eine Option im Anwendungs\-Assistenten unterstützt beide.  Wenn eine Statusleiste vorhanden ist, stellt die Anwendung automatisch hilfreiches Feedback, während der Benutzer den Zeiger über Elemente auf Menüs verschoben.  Die Anwendung wird automatisch eine Aufforderungstext in der Statusleiste an, wenn das Menüelement hervorgehoben wird.  Wenn der Benutzer beispielsweise den Mauszeiger auf den Befehl **Ausschneiden** im Menü **Bearbeiten** bewegt, könnte die Statusleiste "Schnitte die Auswahl und schreibt sie in die Zwischenablage in" Nachrichtenbereich der Statusleiste an.  Die Eingabeaufforderung hilft dem Benutzer, den Zweck des Menüelements zu verstehen.  Dies funktioniert auch, wenn der Benutzer auf eine Schaltfläche klickt.  
  
 Sie können dieser Statusleistenhilfe hinzufügen, indem Sie der Eingabeaufforderungen für Menüelemente definieren, die Sie dem Programm hinzufügen.  Hierzu, stellen Sie die der Eingabeaufforderungen bereit wenn Sie die Eigenschaften des Menüelements im Menü\-Editor bearbeiten.  Die Zeichenfolgen, die Sie definieren, werden in der Ressourcendatei der Anwendung gespeichert; sie dieselben IDs, die die Befehle sie berücksichtigen.  
  
 Standardmäßig fügt der Anwendungs\-Assistent `AFX_IDS_IDLEMESSAGE`, die ID für ein Standard "Bereit" Meldung hinzu, die angezeigt wird, wenn das Programm gewartet neue Meldungen ist.  Wenn Sie die Option der kontextbezogenen Hilfe im Anwendungs\-Assistenten angeben, wird die Nachricht geändert zu "für Hilfe, F1 drücken."  
  
## Siehe auch  
 [Meldungsbehandlung und \-zuordnung](../mfc/message-handling-and-mapping.md)