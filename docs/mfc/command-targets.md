---
title: "Befehlsziele"
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
  - "Befehlszuordnung"
  - "Befehlsrouting, Befehlsziele"
  - "Befehlsziele"
  - "Meldungen, Befehl"
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Befehlsziele
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Abbildung [Befehle im Framework](../mfc/user-interface-objects-and-command-ids.md) zeigt die Verbindung zwischen einem Benutzeroberflächeobjekt, beispielsweise ein Menüelement und die Handlerfunktion an, der das Framework aufruft, um den resultierenden Befehl auszuführen, wenn auf das geklickt wird.  
  
 Windows Meldungen sendet, die nicht Befehlsmeldungen direkt an ein Fenster sind, dessen Handler für die Meldung dann aufgerufen wird.  Allerdings leitet das Framework Befehle zu einigen Kandidatenobjekten \- aufgerufenen "Befehl gilt" ab \- eine weiter, das gewöhnlich einen Handler für den Befehl aufruft.  Die Handlerfunktionen funktionieren genauso für Befehle und Standardwindows\-meldungen, die Mechanismen, durch die sie aufgerufen werden, sind unterschiedlich, wie in [Wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md) erläutert.  
  
## Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)