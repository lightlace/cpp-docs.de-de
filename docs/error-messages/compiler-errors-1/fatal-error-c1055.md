---
title: "Schwerwiegender Fehler C1055"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C1055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1055"
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit: Keine weiteren Symbole  
  
 Die Quelldatei enthält zu viele Symbole.  Der Compiler hatte nicht mehr genügend Hashschlüssel für die Symboltabelle.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Teilen Sie die Quelldatei in kleinere Dateien auf.  
  
2.  Beseitigen Sie überflüssige Headerdateien.  
  
3.  Temporäre und globale Variablen sollten wiederverwendet und nicht neu erstellt werden.