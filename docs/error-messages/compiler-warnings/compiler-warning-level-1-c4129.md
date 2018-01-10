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
ms.workload: cplusplus
ms.openlocfilehash: 6405c7c156f34b49ab892304ee51a6b996ac2595
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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