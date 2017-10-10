---
title: Schwerwiegender Fehler C1054 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1054
dev_langs:
- C++
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d02d8eb05633d7250dc3f7ee85dd78ccf4153052
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1054"></a>Schwerwiegender Fehler C1054
Compilerlimit: zu tiefe Schachtelung von Initialisierungen  
  
 Der Code überschreitet die maximale Schachtelungstiefe für Initialisierer (abhängig von der Kombination von Typen, die derzeit initialisiert die Stufen von 10 bis 15).  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Vereinfachen Sie die Datentypen, die zur Reduzierung der Schachtelungsebenen initialisiert wird.  
  
2.  Initialisieren von Variablen in separaten Anweisungen nach der Deklaration.
