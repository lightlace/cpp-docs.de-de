---
title: "OnCmdMsg-Handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnCmdMsg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlsrouting, OnCmdMsg-Handler"
  - "Handler"
  - "Handler, OnCmdMessage"
  - "Meldungen, Routing"
  - "OnCmdMessage-Methode"
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# OnCmdMsg-Handler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um das Routing von Befehlen zu erreichen, wird jedes Befehlsziel die Memberfunktion `OnCmdMsg` des Befehlsziels in der folgenden Reihenfolge auf.  Befehlsziele verwenden `OnCmdMsg`, um zu bestimmen, ob sie einen Befehl behandeln und einem anderen Befehlsziel übergeben können, wenn sie nicht behandeln können.  
  
 Jede BefehlZielklasse überschreibt möglicherweise die `OnCmdMsg`\-Memberfunktion.  Überschreibungen können jede Klasse Befehle zu einem bestimmten Ziel folgenden weiterleiten.  Ein Rahmenfenster beispielsweise führt immer Befehle zu aktuellen untergeordneten Fenster oder Ansicht, wie in der Tabelle [Standardbefehls\-Route](../mfc/command-routing.md) weiter.  
  
 Die standardmäßige `CCmdTarget` Implementierung von `OnCmdMsg` verwendet die Meldungszuordnung der BefehlZielklasse, um für eine Handlerfunktion für jede Befehlsmeldung zu suchen, die die \- genauso empfängt, dass Standardmeldungen gefunden werden.  Ist eine Übereinstimmung ermittelt, ruft sie den Handler auf.  Das Meldungszuordnungssuchen wird in [Wie das Framework Meldungszuordnungen sucht](../mfc/how-the-framework-searches-message-maps.md) erläutert.  
  
## Siehe auch  
 [Wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md)