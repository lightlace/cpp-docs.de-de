---
title: "Ressourcencompiler: Schwerwiegender Fehler RC1120 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1120"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1120"
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ressourcencompiler: Schwerwiegender Fehler RC1120
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Nicht genügend Arbeitsspeicher,**   
 ***Anzahl* Bytes benötigt**  
  
 Dem Ressourcencompiler stand nicht genügend Arbeitsspeicher für die Elemente zur Verfügung, die in seinem Heap gespeichert werden.  Dies ist in der Regel das Ergebnis zu vieler vorhandener Symbole.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Vergrößern Sie die Windows\-Auslagerungsdatei.  Weitere Informationen über das Vergrößern der Auslagerungsdatei finden Sie unter dem Stichwort "Virtueller Speicher" in der Windows\-Hilfe.  
  
2.  Entfernen Sie unnötige Includedateien, insbesondere nicht benötigte `#define`s und Prototypen von Funktionen.  
  
3.  Teilen Sie die aktuelle Datei in mehrere kleinere Dateien auf, und kompilieren Sie diese separat.  
  
4.  Entfernen Sie andere auf dem Computer ausgeführte Programme und Treiber, die möglicherweise einen wesentlichen Teil des Speichers belegen.