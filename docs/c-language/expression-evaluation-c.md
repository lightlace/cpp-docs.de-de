---
title: Ausdrucksauswertung (C) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 21b78b659b4d4cd8f3bb5db849b3c64a5f66f971
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluation-c"></a>Ausdrucksauswertung (C)
Ausdrücke, die mit Zuweisung, unärem Inkrement bzw. unärem Dekrement zusammenhängen oder eine Funktion aufrufen, können Folgen haben, die mit ihrer Auswertung auftreten (Nebeneffekte). Mit dem Erreichen eines "Sequenzpunkts" wird gewährleistet, dass alles vor dem Sequenzpunkt, einschließlich aller möglichen Nebeneffekte, ausgewertet wurde, bevor die Auswertung von Elementen nach dem Sequenzpunkt fortgesetzt wird.  
  
 "Nebeneffekte" sind die Änderungen, die durch die Auswertung eines Ausdrucks verursacht werden. Nebeneffekte treten auf, wenn der Wert einer Variablen durch eine Ausdrucksauswertung geändert wird. Alle Zuweisungsvorgänge haben Nebeneffekte. Funktionsaufrufe können auch Nebeneffekte haben, wenn sie den Wert eines extern sichtbaren Elements entweder durch direkte oder indirekte Zuweisung über einen Zeiger ändern.  
  
## <a name="see-also"></a>Siehe auch  
 [Operanden und Ausdrücke](../c-language/operands-and-expressions.md)