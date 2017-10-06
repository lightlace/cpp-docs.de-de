---
title: "Übersicht über die Funktionen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C++]
- control flow, function calls
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 16612a32a0e5cb2294f4b74f46c14c206c1cbcbc
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="overview-of-functions"></a>Übersicht über die Funktionen
Funktionen müssen eine Definition aufweisen und sollten eine Deklaration enthalten, obwohl eine Definition als Deklaration verwendet werden kann, wenn die Deklaration vor dem Aufruf der Funktion angezeigt wird. Die Funktionsdefinition enthält den Funktionstext, also den Code, der beim Funktionsaufruf ausgeführt wird.  
  
 Eine Funktionsdeklaration legt den Namen, den Rückgabetyp und die Attribute einer Funktion fest, die an anderer Stelle im Programm definiert ist. Eine Funktionsdeklaration muss dem Aufruf der Funktion vorangestellt sein. Daher werden die Headerdateien, die die Deklarationen für die Laufzeitfunktionen enthalten, im Code vor dem Aufruf einer Laufzeitfunktion eingebunden. Sofern die Deklaration Informationen über die Art und Anzahl der Parameter enthält, ist die Deklaration ein Prototyp. Weitere Informationen finden Sie unter [Funktionsprototypen](../c-language/function-prototypes.md).  
  
 Der Compiler nutzt den Prototyp, um die Argumenttypen bei nachfolgenden Funktionsaufrufen mit den Funktionsparametern zu vergleichen und dann die Argumenttypen (falls notwendig) in die Parametertypen zu konvertieren.  
  
 Ein Funktionsaufruf übergibt die Ausführungssteuerung von der aufrufenden Funktion an die aufgerufene Funktion. Die Argumente, sofern vorhanden, werden nach Wert an die aufgerufene Funktion übergeben. Die Ausführung einer `return`-Anweisung in der aufgerufenen Funktion gibt die Steuerung und ggf. einen Wert an die aufrufende Funktion zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../c-language/functions-c.md)
