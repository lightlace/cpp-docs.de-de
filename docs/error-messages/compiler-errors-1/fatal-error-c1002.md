---
title: Schwerwiegender Fehler C1002 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cab0e1db2d84fb5ba84d773f28e70341faf10ac6
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1002"></a>Schwerwiegender Fehler C1002
Im 2. Durchlauf ist kein Heapspeicher mehr für den Compiler verfügbar.  
  
 Der Compiler genügend Speicherplatz für dynamischen Arbeitsspeicher während des zweiten Durchlaufs, wahrscheinlich aufgrund eines Programms durch zu viele Symbole oder komplexe Ausdrücke.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Unterteilen Sie die Quelldatei in mehrere kleinere Dateien.  
  
2.  Ausdrücke in kleinere Teilausdrücke geteilt.  
  
3.  Entfernen Sie andere Programme oder Treiber, die Arbeitsspeicher nutzen.
