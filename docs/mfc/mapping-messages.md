---
title: "Zuordnen von Meldungen | Microsoft Docs"
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
  - "Befehlszuordnung"
  - "Befehle, Verbinden mit Handlerfunktionen"
  - "Befehle, Zuordnen"
  - "Zuordnungen, Befehle"
  - "Zuordnungen, Meldungen"
  - "Meldungsbehandlung, Verbinden mit Handlerfunktionen"
  - "Meldungszuordnungen, Informationen über Meldungszuordnungen"
  - "Meldungen, Zuordnen"
ms.assetid: 996f0652-0698-4b8c-b893-cdaa836d9d0f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Zuordnen von Meldungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede Frameworkklasse, Meldungen oder Befehle empfangen kann, verfügt eigenen "Meldungszuordnung." Das Framework verwendet Meldungszuordnungen, um Meldungen und Befehle die Handlerfunktionen herzustellen.  Jede Klasse, die von der `CCmdTarget`\-Klasse abgeleitet ist, kann eine Meldungszuordnung haben.  Andere Elemente beschreiben Meldungszuordnungen ausführlich und beschreiben, wie diese verwendet werden.  
  
 Trotz des Namens "Meldungszuordnung," bearbeiten Meldungszuordnungen Meldungen und \- befehlen alle drei Kategorien Meldungen, die in [Meldungs\-Kategorien](../mfc/message-categories.md) aufgeführt sind.  
  
## Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)