---
title: "Compilerwarnung (Stufe 1) C4835 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4835"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4835"
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerwarnung (Stufe 1) C4835
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Variable': Der Initialisierer für exportierte Daten kann erst ausgeführt werden, nachdem der verwaltete Code das erste Mal in der Hostassembly ausgeführt wurde.  
  
 Wenn von verwalteten Komponenten untereinander auf Daten zugegriffen wird, wird empfohlen, keine systemeigenen Import\- und Exportmechanismen zu verwenden.  Deklarieren Sie stattdessen die Datenmember innerhalb eines verwalteten Typs, und verweisen Sie auf die Metadaten im Client mit `#using`.  Weitere Informationen finden Sie unter [\#using\-Direktive](../../preprocessor/hash-using-directive-cpp.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4835 generiert.  
  
```  
// C4835.cpp  
// compile with: /W1 /clr /LD  
int f() { return 1; }  
int n = 9;  
  
__declspec(dllexport) int m = f();   // C4835  
__declspec(dllexport) int *p = &n;   // C4835  
```  
  
## Beispiel  
 Im folgenden Beispiel wird die im vorherigen Beispiel erstellte Komponente verwendet und auf diese Weise verdeutlicht, dass die Werte der Variablen nicht der Erwartung entsprechen.  
  
```  
// C4835_b.cpp  
// compile with: /clr C4835.lib  
#include <stdio.h>  
__declspec(dllimport) int m;  
__declspec(dllimport) int *p;  
  
int main() {  
   printf("%d\n", m);  
   printf("%d\n", p);  
}  
```  
  
  **0**  
**268456008**