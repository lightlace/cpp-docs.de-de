---
title: Compilerwarnung (Stufe 1) C4807 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4807
dev_langs:
- C++
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af604a1a045b9dbef7b3c27f9c7aabd0040aa318
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4807"></a>Compilerwarnung (Stufe 1) C4807
"Operation": Unsichere Kombination von Typ "Typ" und signiertem Bitfeld des Typs "Typ"  
  
 Diese Warnung wird erzeugt, wenn ein vorzeichenbehaftetes Bitfeld der Länge 1 mit einer `bool` -Variablen verglichen wird. Da ein vorzeichenbehaftetes Bitfeld der Länge 1 nur die Werte -1 oder 0 enthalten kann, ist der Vergleich mit einem `bool`-Wert nicht unproblematisch. Keine Warnungen werden dagegen erzeugt, wenn `bool` -Werte mit vorzeichenlosen Bitfeldern der Länge 1 verglichen werden, da diese mit `bool` identisch sind und nur 0 oder 1 enthalten können.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4807 generiert:  
  
```  
// C4807.cpp  
// compile with: /W1  
typedef struct bitfield {  
   signed mybit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bool b = true;  
  
   // try..  
   // int b = true;  
  
   bf.mybit = -1;  
   if (b == bf.mybit) {   // C4807  
      b = false;  
   }  
}  
```