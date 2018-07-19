---
title: Schwerwiegender Fehler C1002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c63a8d399b3e8c781694d89825e7898fd1db4639
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225050"
---
# <a name="fatal-error-c1002"></a>Schwerwiegender Fehler C1002
Im 2. Durchlauf ist kein Heapspeicher mehr für den Compiler verfügbar.  
  
 Der Compiler genügend Speicherplatz für dynamischen Arbeitsspeicher während des zweiten Durchlaufs, wahrscheinlich aufgrund eines Programms durch zu viele Symbole oder komplexe Ausdrücke.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Unterteilen Sie die Quelldatei in mehrere kleinere Dateien.  
  
2.  Ausdrücke in kleinere Teilausdrücke geteilt.  
  
3.  Entfernen Sie andere Programme oder Treiber, die Arbeitsspeicher nutzen.