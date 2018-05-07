---
title: Ausdrucksauswertungsfehler CXX0039 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0039
dev_langs:
- C++
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8681d73d2889433516b205a47c500193bbeabdb0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0039"></a>Ausdrucksauswertungsfehler CXX0039
Symbol ist nicht eindeutig  
  
 Die C-ausdrucksauswertung kann nicht welche Instanz eines Symbols für die Verwendung in einem Ausdruck bestimmt werden. Das Symbol tritt höchstens einmal in der Vererbungsstruktur.  
  
 Sie müssen den Bereichsauflösungsoperator verwenden (`::`) der Instanz, mit der im Ausdruck explizit angeben.  
  
 Dieser Fehler ist mit CAN0039 identisch.