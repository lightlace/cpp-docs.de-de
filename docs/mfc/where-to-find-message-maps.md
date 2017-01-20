---
title: "Wo sich Meldungszuordnungen befinden"
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
  - "Suchen von Meldungszuordnungstabellen"
  - "Makros, Meldungszuordnung"
  - "Meldungszuordnungen, Suchen"
  - "Meldungszuordnungsmakros"
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Wo sich Meldungszuordnungen befinden
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie ein neues Anwendungsskelett mit dem Anwendungs\-Assistenten erstellen, erstellt der Anwendungs\-Assistent eine Meldungszuordnung für jede BefehlZielklasse, die sie für Sie erstellt.  Dies schließt die abgeleitete Anwendung, Dokument, Ansicht und Rahmenfensterklassen ein.  Einige dieser Meldungszuordnungen haben bereits die Einträge, die vom Anwendungs\-Assistenten für bestimmte Meldungen und vordefinierten Befehlen angegeben werden, und einige sind lediglich um Platzhalter für Handler, die Sie hinzufügen.  
  
 Die Meldungszuordnung einer Klasse ist in der CPP\-Datei für die Klasse.  gemeinsam mit den grundlegenden Meldungszuordnungen, die der Anwendungs\-Assistent erstellt wird, verwenden Sie das Eigenschaftenfenster, um Einträge für die Meldungen hinzuzufügen und einen, dass jede Klasse behandelt.  Eine typische Meldungszuordnung könnte folgendermaßen aussehen, nachdem Sie einige Einträge hinzufügen:  
  
 [!CODE [NVC_MFCMessageHandling#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#1)]  
  
 Die Meldungszuordnung besteht aus einer Auflistung aus Makros.  Zwei Makros, [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) und [END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md), markieren die Meldungszuordnung.  Andere Makros, wie `ON_COMMAND`, geben den Inhalt der Meldungszuordnung aus.  
  
> [!NOTE]
>  Die Meldungszuordnungsmakros werden nicht von Semikolons gefolgt.  
  
 Wenn Sie den Hinzufügens\-Klassenassistenten verwenden, um eine neue Klasse erstellen, stellt sie eine Meldungszuordnung für die Klasse.  Alternativ können Sie eine Meldungszuordnung mithilfe des Quellcode\-Editors manuell erstellen.  
  
## Siehe auch  
 [Wie das Framework Meldungszuordnungen durchsucht](../mfc/how-the-framework-searches-message-maps.md)