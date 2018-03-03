---
title: Compilerwarnung (Stufe 4) C4127 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4127
dev_langs:
- C++
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d1a5bbd86b6197907f043478df225dceb79679f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4127"></a>Compilerwarnung (Stufe 4) C4127
Bedingter Ausdruck ist konstant  
  
 Der Kontrollausdruck einer `if` -Anweisung oder `while` -Schleife wird in eine Konstante ausgewertet. Aufgrund ihrer allgemeine idiomatische Verwendung trivialen Konstanten wie z. B. 1 oder `true` lösen keine Warnung aus, es sei denn, sie sind, dass das Ergebnis eines Vorgangs in einem Ausdruck. Wenn der steuernde Ausdruck einer `while` Schleife ist eine Konstante, da die Schleife in der Mitte beendet wird, ersetzen Sie die `while` -Schleife durch eine `for` Schleife. Lassen Sie die Initialisierung, den Beendigungstest und die schleifenerhöhung einer `for` -Schleife, die bewirkt, die Schleife dass zu einer unendlichen, genau wie `while(1)`, und Beenden der Schleife kann aus dem Text der der `for` Anweisung.  
  
 Das folgende Beispiel zeigt zwei Möglichkeiten, C4127 generiert und gezeigt, wie, eine for-Schleife, um die Warnung zu vermeiden:  
  
```  
// C4127.cpp  
// compile with: /W4  
#include <stdio.h>  
int main() {  
   if (1 == 1) {}   // C4127  
   while (42) { break; }   // C4127  
  
   // OK  
   for ( ; ; ) {  
      printf("test\n");  
      break;  
   }  
}  
```