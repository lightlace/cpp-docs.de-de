---
title: "Compilerwarnung (Stufe 1) C4656 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4656"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4656"
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4656
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol': Der Datentyp ist neuer als beim letzten Build oder wurde an anderer Stelle unterschiedlich definiert  
  
 Sie haben seit dem letzten erfolgreichen Build einen Datentyp hinzugefügt oder geändert, wodurch er für den Quellcode neu ist.  **Bearbeiten und Fortfahren** unterstützt keine Änderungen an vorhandenen Datentypen.  
  
 Auf diese Warnung folgt stets ein [Schwerwiegender Fehler C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md).  Weitere Informationen finden Sie unter [Unterstützte Codeänderungen](../Topic/Supported%20Code%20Changes%20\(C++\).md).  
  
### So beseitigen Sie diese Warnung, ohne die aktuelle Debugsitzung zu beenden  
  
1.  Versetzen Sie den Datentyp wieder in den Zustand, der vor Auftreten des Fehlers gültig war.  
  
2.  Wählen Sie im Menü **Debuggen** die Option **Codeänderungen übernehmen**.  
  
### So beseitigen Sie diesen Fehler, ohne den Quellcode zu ändern  
  
1.  Wählen Sie im Menü **Debuggen** die Option **Debuggen beenden**.  
  
2.  Klicken Sie im Menü **Erstellen** auf **Erstellen**.