---
title: "Schwerwiegender Fehler C1509 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1509"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1509"
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Schwerwiegender Fehler C1509
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit: Zu viele Handler für Ausnahmezustände in der Funktion "Funktion". Vereinfachen Sie die Funktion  
  
 Eine interne Beschränkung für Ausnahmehandlerzustände \(32,768\) wird vom Code überschritten.  
  
 Die häufigste Ursache hierfür ist, dass die Funktion einen komplexen Ausdruck benutzerdefinierter Klassenvariablen und arithmetischer Operatoren enthält.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Vereinfachen Sie Ausdrücke, indem Sie temporären Variablen allgemeine Unterausdrücke zuordnen.  
  
2.  Teilen Sie die Funktion in kleinere Funktionen auf.