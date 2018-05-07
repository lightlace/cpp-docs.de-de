---
title: Schwerwiegender Fehler C1055 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1055
dev_langs:
- C++
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07f0dc0e8dca08e8b0de47b73516d3fdfa21435b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1055"></a>Schwerwiegender Fehler C1055
Compilerlimit: keine weiteren Schlüssel  
  
 Die Quelldatei enthält zu viele Symbole. Der Compiler war nicht genügend Hashschlüssel für die Symboltabelle.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Teilen Sie die Quelldatei in kleinere Dateien.  
  
2.  Vermeiden Sie unnötige Headerdateien.  
  
3.  Wiederverwenden von temporären und globale Variablen statt neue zu erstellen.