---
title: Ausdrucksauswertungsfehler CXX0052 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0052
dev_langs: C++
helpviewer_keywords:
- CXX0052
- CAN0052
ms.assetid: 5060d479-d0a4-4682-b858-c8b9a4f324e6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0725d117f6481d2bdc218089a7599502c0f5213d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0052"></a>Ausdrucksauswertungsfehler CXX0052
die Memberfunktion ist nicht vorhanden  
  
 Eine Memberfunktion wurde als einen Haltepunkt angegeben, aber nicht gefunden. Festlegen eines Haltepunkts an eine Funktion, die inline gesetzt wurde, kann dieser Fehler verursacht.  
  
 Kompilieren Sie die Datei mit inlining erzwungen deaktiviert (/ Ob0) einen Haltepunkt in dieser Funktion festlegen.  
  
 Ein Ausdruck, der eine Funktion, die nicht definiert wurde.  
  
 Dieser Fehler ist mit CAN0052 identisch.