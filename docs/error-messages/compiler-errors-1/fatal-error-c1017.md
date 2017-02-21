---
title: "Schwerwiegender Fehler C1017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1017"
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Schwerwiegender Fehler C1017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültiger Ausdruck für Ganzzahlkonstante  
  
 Der Ausdruck in einer `#if`\-Direktive ist entweder nicht vorhanden oder lässt sich nicht als Konstante auswerten.  
  
 Sofern in einer der Direktiven `#if`, `#elif` oder `#else` verwendet, müssen mit `#define` definierte Konstanten über Werte verfügen, die als Ganzzahlkonstanten ausgewertet werden.  
  
 Im folgenden Beispiel wird C1017 generiert:  
  
```  
// C1017.cpp  
#define CONSTANT_NAME "YES"  
#if CONSTANT_NAME   // C1017  
#endif  
```  
  
 Mögliche Lösung:  
  
```  
// C1017b.cpp  
// compile with: /c  
#define CONSTANT_NAME 1  
#if CONSTANT_NAME  
#endif  
```  
  
 Da `CONSTANT_NAME` als Zeichenfolge und nicht als ganze Zahl ausgewertet wird, wird durch die `#if`\-Direktive der schwerwiegende Fehler C1017 generiert.  
  
 In anderen Fällen wird eine nicht definierte Konstante vom Präprozessor mit 0 ausgewertet.  Dies kann, wie im folgenden Beispiel veranschaulicht, zu unerwarteten Ergebnissen führen.  Da `YES` nicht definiert ist, hat die Auswertung das Ergebnis 0.  Der Ausdruck `#if` `CONSTANT_NAME` wird mit False ausgewertet, und der Code, der für `YES` verwendet werden soll, wird vom Präprozessor entfernt.  Da auch `NO` nicht definiert ist \(0\), wird `#elif` `CONSTANT_NAME==NO` mit True \(`0 == 0`\) ausgewertet, wodurch der Code im `#elif`\-Abschnitt der Anweisung vom Präprozessor nicht berücksichtigt wird – also genau das Gegenteil des beabsichtigten Verhaltens eintritt.  
  
```  
// C1017c.cpp  
// compile with: /c  
#define CONSTANT_NAME YES  
#if CONSTANT_NAME  
   // Code to use on YES...  
#elif CONSTANT_NAME==NO  
   // Code to use on NO...  
#endif  
```  
  
 Um die Verarbeitung von Präprozessordirektiven durch den Compiler exakt nachzuvollziehen, verwenden Sie [\/P](../../build/reference/p-preprocess-to-a-file.md), [\/E](../../build/reference/e-preprocess-to-stdout.md) oder [\/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).