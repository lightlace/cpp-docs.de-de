---
title: "Verwenden von Extraktionsoperatoren | Microsoft Docs"
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
helpviewer_keywords: 
  - ">>-Operator, Extraktionsoperatoren"
  - "Extraktionsoperatoren"
  - "Operatoren [C++], Extrahierung"
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Verwenden von Extraktionsoperatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Extraktionsoperator \(`>>`\), das für alle Standard\-C\+\+\-Datentypen vorprogrammiert wird, besteht die einfachste Methode, Bytes von einem Eingabestreamobjekt abzurufen.  
  
 Eingabe\-Extraktionsoperatoren des formatierten Texts hängen von den Leerzeichen, um eingehende Datenwerte zu trennen.  Dies ist schwierig, wenn ein Textfeld mehrere Wörter enthält, oder wenn Zahlen Kommas trennen.  In einem solchen Fall ist eine Alternative, die unformatierte Eingabememberfunktion [istream::getline](../Topic/basic_istream::getline.md) verwenden, um einen Textblock mit den verfügbaren Leerraum gelesen, anschließend analysiert den Block mit speziellen Funktionen.  Eine andere Methode ist, eine Eingabestreamklasse mit einer Memberfunktion wie `GetNextToken` zu berechnen, die istream Member, um zu extrahieren und Formatzeichendaten aufrufen kann.  
  
## Siehe auch  
 [Eingabestreams](../standard-library/input-streams.md)