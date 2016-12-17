---
title: "&#220;bersicht &#252;ber die Funktionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Ablaufsteuerung, Funktionsaufrufe"
  - "Funktionen [C++]"
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;bersicht &#252;ber die Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Funktionen müssen eine Definition aufweisen und sollten eine Deklaration enthalten, obwohl eine Definition als Deklaration verwendet werden kann, wenn die Deklaration vor dem Aufruf der Funktion angezeigt wird.  Die Funktionsdefinition enthält den Funktionstext, also den Code, der beim Funktionsaufruf ausgeführt wird.  
  
 Eine Funktionsdeklaration legt den Namen, den Rückgabetyp und die Attribute einer Funktion fest, die an anderer Stelle im Programm definiert ist.  Eine Funktionsdeklaration muss dem Aufruf der Funktion vorangestellt sein.  Daher werden die Headerdateien, die die Deklarationen für die Laufzeitfunktionen enthalten, im Code vor dem Aufruf einer Laufzeitfunktion eingebunden.  Sofern die Deklaration Informationen über die Art und Anzahl der Parameter enthält, ist die Deklaration ein Prototyp.  Weitere Informationen finden Sie unter [Funktionsprototypen](../c-language/function-prototypes.md).  
  
 Der Compiler nutzt den Prototyp, um die Argumenttypen bei nachfolgenden Funktionsaufrufen mit den Funktionsparametern zu vergleichen und dann die Argumenttypen \(falls notwendig\) in die Parametertypen zu konvertieren.  
  
 Ein Funktionsaufruf übergibt die Ausführungssteuerung von der aufrufenden Funktion an die aufgerufene Funktion.  Die Argumente, sofern vorhanden, werden nach Wert an die aufgerufene Funktion übergeben.  Die Ausführung einer `return`\-Anweisung in der aufgerufenen Funktion gibt die Steuerung und ggf. einen Wert an die aufrufende Funktion zurück.  
  
## Siehe auch  
 [Funktionen](../c-language/functions-c.md)