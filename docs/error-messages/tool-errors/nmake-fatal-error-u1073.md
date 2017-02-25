---
title: "NMAKE: Schwerwiegender Fehler U1073 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1073"
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE: Schwerwiegender Fehler U1073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Zielname" konnte nicht erstellt werden  
  
 Das angegebene Ziel ist nicht vorhanden, und es ist weder ein Befehl auszuführen noch eine Rückschlussregel anzuwenden.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Überprüfen Sie die Rechtschreibung des Zielnamens.  
  
2.  Falls es sich bei *Zielname* um ein Pseudoziel handelt, geben Sie ihn als Ziel in einem anderen Beschreibungsblock an.  
  
3.  Falls es sich bei *Zielname* um einen Makroaufruf handelt, stellen Sie sicher, dass er zu keiner NULL\-Zeichenfolge erweitert wird.