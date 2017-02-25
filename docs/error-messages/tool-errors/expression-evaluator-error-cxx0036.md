---
title: "Ausdrucksauswertungsfehler CXX0036 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0036"
  - "CXX0036"
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausdrucksauswertungsfehler CXX0036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehlerhafte Kontextangabe {...}  
  
 Diese Meldung kann bei fehlerhafter Verwendung des Operators Kontext \(**{}**\) generiert werden.  
  
-   Die Syntax des Operators Kontext \(**{}**\) war nicht korrekt.  
  
     Die Syntax des Operators Kontext lautet:  
  
     {*function*,*module*,*dll*}*expression*  
  
     Dies gibt den Kontext von *expression* an.  Der Operator Kontext besitzt den gleichen Vorrang und wird so wie eine Typkonvertierung verwendet.  
  
     Abschließende Kommas können ausgelassen werden.  Wenn *function*, *module* oder *dll* ein Komma enthält, muss der gesamte Name in Klammern eingeschlossen werden.  
  
-   Der Funktionsname wurde fehlerhaft buchstabiert oder ist im angegebenen Modul oder in der DLL \(Dynamic Link Library\) nicht vorhanden.  
  
     Da von C Groß\-\/Kleinschreibung beachtet wird, muss *function* genau so eingegeben werden, wie es in der Quelle definiert wurde.  
  
-   Das Modul oder die DLL konnte nicht gefunden werden.  
  
     Überprüfen Sie den vollständigen Pfadnamen des angegebenen Moduls oder der DLL.  
  
 Dieser Fehler ist mit CAN0036 identisch.