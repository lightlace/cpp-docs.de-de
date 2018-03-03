---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1120 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1120
dev_langs:
- C++
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28a35cc2f932cdf655324d05c10bdb875aa895a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Ressourcencompiler: Schwerwiegender Fehler RC1120
nicht genügend Arbeitsspeicher benötigt Anzahl bytes  
  
 Der Ressourcencompiler war nicht genügend Speicher für Elemente, die in einen Heap gespeichert wird. In der Regel ist dies das Ergebnis, dass zu viele Symbole.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Erhöhen Sie die Windows-Auslagerungsdatei. Weitere Informationen zum Vergrößern der Auslagerungsdatei finden Sie unter Virtueller Arbeitsspeicher im Windows-Hilfe.  
  
2.  Löschen Sie überflüssige Includedateien, insbesondere nicht benötigte `#define`s und Prototypen.  
  
3.  Die aktuelle Datei in zwei oder mehr Dateien aufteilen und diese separat kompilieren.  
  
4.  Entfernen Sie andere Programme oder Treiber, die im System, das viel Arbeitsspeicher belegen ausgeführt werden.