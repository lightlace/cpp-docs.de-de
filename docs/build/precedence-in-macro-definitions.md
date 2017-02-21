---
title: "Vorrang bei Makrodefinitionen | Microsoft Docs"
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
  - "Makros, Rangfolge"
  - "NMAKE (Programm), Rangfolge bei Makrodefinitionen"
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Vorrang bei Makrodefinitionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn ein Makro mehrere Definitionen besitzt, wird von NMAKE die ranghöchste Definition verwendet.  Die folgende Liste zeigt die Reihenfolge des Vorrangs von oben nach unten an:  
  
1.  ein Makro, das in der Befehlszeile definiert wurde  
  
2.  ein Makro, das in einem Makefile oder einer Includedatei definiert wurde  
  
3.  ein geerbtes Umgebungsvariablenmakro  
  
4.  ein in der Datei Tools.ini definiertes Makro  
  
5.  ein vordefiniertes Makro wie [CC](../build/command-macros-and-options-macros.md) und [AS](../build/command-macros-and-options-macros.md)  
  
 Makros werden von Umgebungsvariablen mit \/E geerbt, um Makefilemakros mit dem gleichen Namen zu überschreiben.  Eine Befehlszeile wird mit **\!UNDEF** überschrieben.  
  
## Siehe auch  
 [Definieren eines NMAKE\-Makros](../build/defining-an-nmake-macro.md)