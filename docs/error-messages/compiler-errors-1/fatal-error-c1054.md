---
title: Schwerwiegender Fehler C1054 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1054
dev_langs:
- C++
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9daac4944c57dbf08fe0ebcbc95993a97838585
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198897"
---
# <a name="fatal-error-c1054"></a>Schwerwiegender Fehler C1054
Compilerlimit: zu tiefe Schachtelung von Initialisierungen  
  
 Der Code überschreitet die maximale Schachtelungstiefe für Initialisierer (abhängig von der Kombination von Typen, die derzeit initialisiert die Stufen von 10 bis 15).  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Vereinfachen Sie die Datentypen, die zur Reduzierung der Schachtelungsebenen initialisiert wird.  
  
2.  Initialisieren von Variablen in separaten Anweisungen nach der Deklaration.