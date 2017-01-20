---
title: "Benutzeroberfl&#228;chenobjekte und Befehls-IDs"
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
  - "Befehlsbehandlung, Benutzerschnittstellenobjekte"
  - "Befehls-IDs, Benutzerschnittstellenobjekte"
  - "Befehlsrouting, MFC"
  - "Tastenkombinationen, Zuordnung mit IDs"
  - "Menüelemente, Zuordnung mit IDs"
  - "MFC, Befehlsrouting"
  - "Symbolleisten-Steuerelemente [MFC], Befehls-ID"
  - "Benutzerschnittstellenobjekte, Zuordnung mit IDs"
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Benutzeroberfl&#228;chenobjekte und Befehls-IDs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Menüelemente, Symbolleistenschaltflächen und Zugriffstasten Benutzeroberfläche sind "Objekte" Lage zum Generieren von Befehlen.  Die einzelnen Benutzeroberflächeobjekt hat die ID  Sie ordnen ein Benutzeroberflächeobjekt mit einem Befehl zu, indem Sie die gleiche ID auf das Objekt und dem Befehl zuweisen.  Wie in [Meldungen](../mfc/messages.md) erläutert, werden als Befehle Sondermeldungen implementiert.  Die Abbildung "Befehle im Framework" unten zeigt, wie das Framework Befehle verwaltet.  Wenn ein Benutzeroberflächeobjekt generiert, behandelt ein Befehl, wie `ID_EDIT_CLEAR_ALL`, eines der Objekte in der Anwendung den Befehl \- in der folgenden Abbildung, wird die `OnEditClearAll`\-Funktion des document\-Objekts zur Meldungszuordnung des Dokuments aufgerufen.  
  
 ![Befehle im Framework](../mfc/media/vc385p1.png "vc385P1")  
Befehle im Framework  
  
 Die Abbildung "Befehl, der im Framework" unten wird aktualisiert, wie MFC Benutzeroberflächen\-Objekte wie Menüelemente und Symbolleisten\-Schaltflächen aktualisiert.  Bevor ein Menü unten oder während der Leerlaufschleife im Fall der Symbolleisten\-Schaltflächen zurückgestellt, MFC\-Routen Updates\-Befehl ein.  In der Abbildung unten, in den Dokumentobjektaufrufen sein Updatebefehlshandler, `OnUpdateEditClearAll`, das Benutzeroberflächeobjekt aktivieren oder deaktivieren.  
  
 ![Befehlsaktualisierung im Framework](../mfc/media/vc385p2.png "vc385P2")  
Befehlsaktualisierung im Framework  
  
## Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)