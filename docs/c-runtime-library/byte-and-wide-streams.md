---
title: "Byte- und weite Streams | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Byte and Wide Streams"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bytestreams"
  - "Breite Streams"
ms.assetid: 61ef0587-4cbc-4eb8-aae5-4c298dbbc6f9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Byte- und weite Streams
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Bytestrom behandelt eine Datei als Bytesequenz.  Innerhalb des Programms wird der Stream die identische Bytesequenz.  
  
 Dagegen behandelt ein breiter Stream eine Datei als Sequenz von generalisierten Mehrbytezeichen, die ein eine Reihe von Codierungsregeln haben können. \(Text und Binärdateien werden zwar gelesen und geschrieben, wie zuvor beschrieben.\) Innerhalb des Programms wird der Stream wie die entsprechende Sequenz von Breitzeichen aus.  Konvertierungen zwischen den zwei Darstellungen treten in der C\-Standardbibliothek auf.  Die \- Konvertierungsregeln können über einen Aufruf von [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) prinzipiell geändert werden, der die Kategorie `LC_CTYPE` ändert.  Jeder breite Stream bestimmt die Konvertierungsregeln, als er weit ausgerichtet ist, und behält diese Regeln bei, wenn die Kategorie `LC_CTYPE` anschließend ändern.  
  
 Das Positionierung innerhalb eines breiten Streams ausgesetzt ist die gleichen Beschränkungen wie für Textdämpfe.  Darüber hinaus quillt möglicherweise der Stellungsanzeiger müssen eine Codierung des Elements Zustandabhängigen verarbeiten hervor.  In der Regel wird jedoch einen Byteoffset im Stream und ein Objekt vom Typ `mbstate_t`.  Daher ist die einzige zuverlässige Methode, eine innerhalb Dateiposition eines breiten Streams abzurufen, indem die [fgetpos](../c-runtime-library/reference/fgetpos.md) aufgerufen wird, und die einzige zuverlässige Methode, eine Position wiederherzustellen erhielt diese Methode ist, indem die [fsetpos](../c-runtime-library/reference/fsetpos.md) aufgerufen wurden.  
  
## Siehe auch  
 [Dateien und Streams](../c-runtime-library/files-and-streams.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)