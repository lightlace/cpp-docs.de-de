---
title: Compilerwarnung (Stufe 1) C4129 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4129
dev_langs:
- C++
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc095a32e5cb0d5a0bf240282e11c3fa3382ffe5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4129"></a>Compilerwarnung (Stufe 1) C4129 generiert
"Character": Unbekannte Escape-Zeichensequenz  
  
 Die `character` hinter einem umgekehrten Schrägstrich (\\) in ein Zeichen oder eine Zeichenfolge Konstante nicht als gültige Escape-Sequenz erkannt wird. Der umgekehrte Schrägstrich wird ignoriert und nicht gedruckt. Das Zeichen hinter dem umgekehrten Schrägstrich wird gedruckt.  
  
 Um einen einzelnen umgekehrten Schrägstrich drucken möchten, geben Sie einen doppelten umgekehrten Schrägstrich (\\\\).  
  
 Der C++-standard, in Abschnitt 2.13.2 erläutert Escapesequenzen.  
  
 Im folgende Beispiel wird C4129 generiert:  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```