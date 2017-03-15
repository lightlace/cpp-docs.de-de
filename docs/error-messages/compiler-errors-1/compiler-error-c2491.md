---
title: "Compilerfehler C2491 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2491"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2491"
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2491
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Definition von Dllimport\-Funktion nicht zulässig  
  
 Daten, statische Datenmember und Funktionen können als `dllimport`s deklariert werden, jedoch nicht als `dllimport`s definiert werden.  
  
 Um dieses Problem zu beheben, entfernen Sie den `__declspec(dllimport)`\-Bezeichner aus der Definition der Funktion.  
  
 Im folgenden Beispiel wird C2491 generiert:  
  
```  
// C2491.cpp  
// compile with: /c  
// function definition  
void __declspec(dllimport) funcB() {}   // C2491  
  
// function declaration  
void __declspec(dllimport) funcB();   // OK  
```