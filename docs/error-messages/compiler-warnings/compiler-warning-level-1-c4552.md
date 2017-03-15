---
title: "Compilerwarnung (Stufe 1) C4552 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4552"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4552"
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4552
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Operator hat keine Auswirkungen; Operator mit Nebeneffekt erwartet  
  
 Wenn eine Ausdrucksanweisung einen Operator ohne Nebeneffekte am Anfang des Ausdrucks hat, liegt wahrscheinlich ein Fehler vor.  
  
 Setzen Sie den Ausdruck in Klammern, um diese Warnung zu deaktivieren.  
  
 Im folgenden Beispiel wird C4552 generiert:  
  
```  
// C4552.cpp  
// compile with: /W1  
int main() {  
   int i, j;  
   i + j;   // C4552  
   // try the following line instead  
   // (i + j);  
}  
```