---
title: Ausdrucksauswertungsfehler CXX0052 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0052
dev_langs:
- C++
helpviewer_keywords:
- CXX0052
- CAN0052
ms.assetid: 5060d479-d0a4-4682-b858-c8b9a4f324e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9f4b6fb0db87a77f433775fedea9880f3f24bd9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0052"></a>Ausdrucksauswertungsfehler CXX0052
die Memberfunktion ist nicht vorhanden  
  
 Eine Memberfunktion wurde als einen Haltepunkt angegeben, aber nicht gefunden. Festlegen eines Haltepunkts an eine Funktion, die inline gesetzt wurde, kann dieser Fehler verursacht.  
  
 Kompilieren Sie die Datei mit inlining erzwungen deaktiviert (/ Ob0) einen Haltepunkt in dieser Funktion festlegen.  
  
 Ein Ausdruck, der eine Funktion, die nicht definiert wurde.  
  
 Dieser Fehler ist mit CAN0052 identisch.