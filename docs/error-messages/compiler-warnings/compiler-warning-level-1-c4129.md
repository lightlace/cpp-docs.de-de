---
title: Compilerwarnung (Stufe 1) C4129 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4129
dev_langs: C++
helpviewer_keywords: C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1efeca1e597af8e7f96b2854fcbcfc49b000009a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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