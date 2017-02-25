---
title: "Compilerwarnung (Stufe 1) C4657 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4657"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4657"
ms.assetid: eb750050-cea6-4ead-b80c-d5dcd4971cfc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4657
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Ausdruck bezieht einen Datentyp ein, der seit dem letzten Build neu hinzugekommen ist.  
  
 Sie haben einen Datentyp hinzugefügt oder geändert, der seit dem letzten erfolgreichen Build neu zum Quellcode hinzugekommen ist. „Bearbeiten und fortfahren“ unterstützt keine Änderungen an vorhandenen Datentypen.  
  
 Auf diese Warnung folgt immer [Schwerwiegender Fehler C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Weitere Informationen hierzu finden Sie unter [Unterstützte Codeänderungen](../Topic/Supported%20Code%20Changes%20\(C++\).md).  
  
### So entfernen Sie diese Warnung, ohne die aktuelle Debugsitzung zu beenden  
  
1.  Ändern Sie den Datentyp wieder in den Zustand, den er vor dem Fehler hatte.  
  
2.  Wählen Sie im Menü **Debuggen** den Befehl **Codeänderungen übernehmen** aus.  
  
### So entfernen Sie diesen Fehler, ohne den Quellcode zu ändern  
  
1.  Wählen Sie im Menü **Debuggen** die Option **Debuggen beenden**.  
  
2.  Wählen Sie im Menü **Erstellen** den Befehl **Erstellen** aus.