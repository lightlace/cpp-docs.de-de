---
title: "Hinzuf&#252;gen eines ATL-Meldungshandlers | Microsoft Docs"
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
  - "ATL, Meldungshandler"
  - "ATL, Fenster"
  - "message handlers [C++]"
  - "message handling [C++], ATL message handler"
  - "windows [C++], ATL"
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Hinzuf&#252;gen eines ATL-Meldungshandlers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um einen Meldungshandler \(eine Memberfunktion der Windows\-Meldungen verarbeitet\) einem Steuerelement hinzuzufügen, wählen Sie zuerst das Steuerelement in der Klassenansicht aus.  Öffnen Sie dann das Fenster **Eigenschaften**, aktivieren Sie das **Meldungen** Symbol aus, und klicken Sie auf das Dropdownfeld im Feld gegenüberliegenden der erforderlichen Meldung.  Dadurch wird eine Deklaration für den Meldungshandler in der Headerdatei und in einem Implementierungsskelett des Steuerelements des Handlers in der CPP\-Datei des Steuerelements hinzu.  Außerdem fügt die Meldungszuordnung hinzu und fügt einen Eintrag für den Handler hinzu.  
  
 Erstellen eines Meldungshandler in ATL hinzuzufügen ist mit dem Hinzufügen eines Meldungshandlers auf eine MFC\-Klasse ähnlich.  Siehe [Hinzufügen eines MFC\-Meldungshandlers](../mfc/reference/adding-an-mfc-message-handler.md) weitere Informationen.  
  
 Die folgenden Bedingungen gelten nur für das Hinzufügen eines ATL\-Meldungshandlers zu:  
  
-   Die Meldungshandler verwenden dieselbe Namenskonvention wie MFC.  
  
-   Die neuen Meldungszuordnungseinträge werden in die zentrale Meldungszuordnung hinzugefügt.  Der Assistent erkennt keine alternative Meldungszuordnungen und Verketten.  
  
## Siehe auch  
 [Implementing a Window](../atl/implementing-a-window.md)