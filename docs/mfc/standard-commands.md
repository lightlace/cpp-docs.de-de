---
title: "Standardbefehle | Microsoft Docs"
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
  - "Befehls-IDs, Standardbefehle"
  - "Befehle [C++], Standard"
  - "Standardbefehle des Bearbeiten-Menüs"
  - "Datei (Menü)"
  - "Hilfe, Menüs"
  - "Bezeichner [C++], Befehls-IDs"
  - "OLE-Befehle"
  - "Programmiererdefinierte IDs [C++]"
  - "Standardbefehle-IDs"
  - "Standardbefehle"
  - "Befehle im Menü "Ansicht""
  - "Befehle im Menü "Fenster""
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Standardbefehle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Framework definiert viele Standardbefehlsmeldungen.  Die IDs für diese Befehle werden normalerweise die Form:  
  
 **ID\_** *Source\_Item*  
  
 wobei *Quelle* normalerweise handelt, besteht ein Menü Name und *ein Element* ein Menüelement.  So ist beispielsweise die Befehls\-ID für den neuen Befehl im Menü Datei `ID_FILE_NEW`.  Standardbefehls\-IDs werden in Fettdruck Buchstabe in die Dokumentation angezeigt.  Programmierer\-definierte IDs werden in einer Schriftart veranschaulicht, die auf den umgebenden Text anders ist.  
  
 In der folgenden Liste werden einige der wichtigsten unterstützten Befehle:  
  
 *Menü Datei\-Befehle*  
 Neu, Öffnen, Schließen, speichern, speichern, z Seiteneinrichtung, Drucks\-Setup, Drucken, Seitenansicht, Beendigungen und zuletzt verwendeten Dateien.  
  
 *Bearbeitungs\-Menübefehle*  
 Löschen, löschen Sie alle, Kopieren, Ausschneiden, Suchen, Einfügen, Wiederholung, ersetzen Sie, wählen Sie alle aus, von Rückgängigmachen und Sie überprüfen.  
  
 *Befehle im Menü "Ansicht"*  
 Symbol\- und Statusleiste.  
  
 *Befehle im Menü "Fenster"*  
 Neu, ordnen Sie an, überlappen Sie, ordnen Sie horizontale, Kachel\-Vertikale und Unterteilen an.  
  
 *Befehle im Menü "Hilfe"*  
 Indizieren Sie, mit der Hilfe und ungefähr.  
  
 *OLE Befehle \(Bearbeitungs\-Menü\)*  
 Neues Objekt Einfüge\-, Links bearbeiten, Pasten\-Link, Inhalte und einfügen *Typname*\-Objekt \(Verbbefehle\).  
  
 Das Framework stellt unterschiedlichem der Unterstützung für diese Befehle bereit.  Einige Befehle sind nur als definierter Befehls\-IDs unterstützt, während andere mit gründlichen Implementierungen unterstützt werden.  Beispielsweise implementiert das Framework den geöffneten Befehl im Menü Datei auf das Erstellen eines neuen document\-Objekts, Anzeigen eines geöffneten Dialogfeld und das Öffnen und Lesen der Datei.  Dagegen müssen Sie Befehle im Menü Bearbeiten selbst implementieren, wie Befehle wie **ID\_EDIT\_COPY** von der Art der Daten abhängig sind, die Sie kopieren.  
  
 Weitere Informationen zu den Befehlen, die unterstützt werden und welche Ebene der Implementierung bereitgestellt, finden Sie unter [Technischer Hinweis 22](../mfc/tn022-standard-commands-implementation.md).  Die Standardbefehle werden in der Datei AFXRES.H. definiert.  
  
## Siehe auch  
 [Benutzeroberflächenobjekte und Befehls\-IDs](../mfc/user-interface-objects-and-command-ids.md)