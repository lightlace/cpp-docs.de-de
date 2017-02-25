---
title: "Schwerwiegender Fehler C1054 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1054"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1054"
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Schwerwiegender Fehler C1054
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit: Initialisierer zu tief geschachtelt  
  
 Die Schachtelungstiefe für Initialisierer \(abhängig von der Kombination der initialisierten Typen 10\-15 Ebenen\) wird vom Code überschritten.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Vereinfachen Sie die zu initialisierenden Datentypen, um die Schachtelungstiefe zu verringern.  
  
2.  Initialisieren Sie Variablen in separaten Anweisungen nach der Deklaration.