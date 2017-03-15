---
title: "Compilerwarnung (Stufe 1) C4145 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4145"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4145"
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4145
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Ausdruck1": Relationaler Ausdruck als Schalterausdruck; mögliche Verwechslung mit "Ausdruck2"  
  
 Eine `switch`\-Anweisung verwendet einen relationalen Ausdruck als Steuerungsausdruck, was einen booleschen Wert für die **case**\-Anweisungen zur Folge hat. Meinten Sie *Ausdruck2*?  
  
## Beispiel  
 Im folgenden Beispiel wird C4145 generiert:  
  
```  
// C4145.cpp // compile with: /W1 int main() { int i = 0; switch(i == 1) {   // C4145, use i instead of i == 1 to resolve case 1: break; default: break; } }  
```