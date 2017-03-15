---
title: "Ausdrucksauswertungsfehler CXX0033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0033"
  - "CXX0033"
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausdrucksauswertungsfehler CXX0033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler in OMF\-Typinformationen  
  
 Die ausführbare Datei verfügt über kein gültiges OMF \(Object Module Format\) zum Debuggen.  
  
 Dieser Fehler ist mit CAN0033 identisch.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die ausführbare Datei wurde nicht mit dem Linker erstellt, der in dieser Version von Visual C\+\+ enthalten ist.  Verknüpfen Sie den Objektcode mit der aktuellen Version von **LINK.EXE** neu.  
  
2.  Die EXE\-Datei ist möglicherweise beschädigt.  Kompilieren und verknüpfen Sie das Programm neu.