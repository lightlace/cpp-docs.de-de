---
title: "&#220;berpr&#252;fen von Extraktionen"
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
  - "Extraktionsfehler"
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: 9
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# &#220;berpr&#252;fen von Extraktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Geben Sie den Fehler, der die Funktionen verarbeitet, erläutert in [Fehler, der Funktionen verarbeitet](../standard-library/output-file-stream-member-functions.md) aus, treffen Sie auf Eingabestreams zu.  Tests für Fehler während der Suche sind wichtig.  Betrachten Sie die folgende Anweisung:  
  
```  
cin >> n;  
```  
  
 Wenn `n` eine Zahl mit Vorzeichen, ein Wert, der größer ist, als 32.767 \(der maximale zulässige Wert oder MAX\_INT\) das `fail` Bit des Streams festgelegt, und das `cin`\-Objekt ist unbrauchbar.  Alle folgenden Extraktion ergeben eine unmittelbare Rückgabe ohne den gespeicherten Wert.  
  
## Siehe auch  
 [Eingabestreams](../standard-library/input-streams.md)