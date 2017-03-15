---
title: "Funktionstypen | Microsoft Docs"
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
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Funktionstypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt zwei Typen von Funktionen.  Eine Funktion, die einen Stapelrahmen erfordert, wird als Rahmenfunktion bezeichnet.  Eine Funktion, die keinen Stapelrahmen erfordert, wird als Endfunktion bezeichnet.  
  
 Eine Rahmenfunktion ist eine Funktion, die Stapelspeicher zuweist, andere Funktionen aufruft, nicht flüchtige Register speichert oder eine Ausnahmebehandlung verwendet.  Außerdem erfordert sie einen Funktionstabelleneintrag.  Eine Rahmenfunktion benötigt einen Prolog und einen Epilog.  Eine Rahmenfunktion kann Stapelspeicher dynamisch zuordnen und einen Framezeiger verwenden.  Ihr steht der volle Funktionsumfang dieses Aufrufstandards zur Verfügung.  
  
 Wenn eine Rahmenfunktion keine andere Funktion aufruft, muss sie nicht den Stapel ausrichten \(siehe den Abschnitt [Stapelreservierung](../build/stack-allocation.md)\).  
  
 Eine Endfunktion benötigt keinen Funktionstabelleneintrag.  Sie kann keine Funktionen aufrufen, keinen Speicherplatz zuweisen und keine nicht flüchtigen Register speichern.  Sie kann bei der Ausführung einen Stapel unausgerichtet verlassen.  
  
## Siehe auch  
 [Verwendung von Stapeln](../build/stack-usage.md)