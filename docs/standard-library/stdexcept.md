---
title: '&lt;stdexcept&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <stdexcept>
dev_langs: C++
helpviewer_keywords: stdexcept header
ms.assetid: 495c10b1-1e60-4514-9f8f-7fda11a2f522
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b67e1bdd9377c81965dd212836e0f224ff618788
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ltstdexceptgt"></a>&lt;stdexcept&gt;
Definiert einige Standardklassen, die zum Berichten von Ausnahmen verwendet werden. Die Klassen bilden eine Ableitungshierarchie, sind alle aus der Klasse [exception](../standard-library/exception-class.md) abgeleitet und enthalten zwei allgemeine Typen von Ausnahmen: logische Fehler und Laufzeitfehler. Die logischen Fehler sind vom Programmierer verursachte Fehler. Sie sind aus der Basisklasse "logic_error" abgeleitet und enthalten:  
  
-   `domain_error`  
  
-   `invalid_argument`  
  
-   `length_error`  
  
-   `out_of_range`  
  
 Die Laufzeitfehler treten aufgrund von Fehlern auf, die es in den Bibliotheksfunktionen oder im Laufzeitsystem gibt. Sie sind aus der Basisklasse "runtime_error" abgeleitet und enthalten:  
  
-   `overflow_error`  
  
-   `range_error`  
  
-   `underflow_error`  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[domain_error-Klasse](../standard-library/domain-error-class.md)|Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Domänenfehler zu melden.|  
|[invalid_argument-Klasse](../standard-library/invalid-argument-class.md)|Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um ein ungültiges Argument zu melden.|  
|[length_error-Klasse](../standard-library/length-error-class.md)|Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Versuch zu melden, ein Objekt zu erstellen, das zu lang ist, um angegeben werden zu können.|  
|[logic_error-Klasse](../standard-library/logic-error-class.md)|Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um Fehler zu melden, die mutmaßlich vor einer Programmausführung erkennbar sind, etwa Verletzungen von logischen Vorbedingungen.|  
|[out_of_range-Klasse](../standard-library/out-of-range-class.md)|Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um ein Argument zu melden, dessen Wert außerhalb seines zulässigen Bereichs liegt.|  
|[overflow_error-Klasse](../standard-library/overflow-error-class.md)|Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen arithmetischen Überlauf zu melden.|  
|[range_error-Klasse](../standard-library/range-error-class.md)|Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Bereichsfehler zu melden.|  
|[runtime_error-Klasse](../standard-library/runtime-error-class.md)|Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um Fehler zu melden, die mutmaßlich nur erkennbar sind, wenn das Programm ausgeführt wird.|  
|[underflow_error-Klasse](../standard-library/underflow-error-class.md)|Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen arithmetischen Unterlauf zu melden.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

