---
title: "Compilerwarnung (Stufe 1) C4552"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4552"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4552"
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
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