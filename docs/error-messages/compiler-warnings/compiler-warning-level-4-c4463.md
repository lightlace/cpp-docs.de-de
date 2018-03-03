---
title: Compilerwarnung (Stufe 4) C4463 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4463
dev_langs:
- C++
helpviewer_keywords:
- C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 71b438de515a4fd01e7714de685ee0a89adb609e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4463"></a>Compilerwarnung (Stufe 4) C4463  
  
> Überlauf; Zuweisen von *Wert* Bitfeld, das nur Werte aus enthalten können *Low_value* auf *High_value*  
  
Die zugewiesene *Wert* liegt außerhalb des Bereichs von Werten, die das Bitfeld aufnehmen kann. Typen mit Vorzeichen Bitfeld verwenden die höherwertigen bit für das Zeichen, wenn also  *n*  ist die Größe des Bereichs Bitfeld mit Vorzeichen von Bitfeldern-2<sup>n-1</sup> 2<sup>n-1</sup>1, während ohne Vorzeichen von Bitfeldern haben einen Bereich von 0 bis 2<sup>n</sup>-1.  
  
## <a name="example"></a>Beispiel  
  
In diesem Beispiel wird C4463 generiert, weil er versucht, einen Wert von 3 auf ein Bitfeld des Typs zuzuweisen `int` mit einer Länge von 2, die über einen Bereich von-2 bis 1 verfügt.  
  
Um dieses Problem zu beheben, können Sie den zugewiesenen Wert auf einen anderen Wert im zulässigen Bereich ändern. Das Bitfeld zum Aufnehmen von Werten ohne Vorzeichen im Bereich von 0 bis 3 vorgesehen ist, können Sie ändern den Deklarationstyp, `unsigned`. Wenn das Feld zum Speichern der Werte in-4 bis 3 Bereich vorgesehen ist, können Sie die Größe der Bitfeld auf 3 ändern.  
  
```cpp  
// C4463_overflow.cpp
// compile with: cl /W4 /EHsc C4463_overflow.cpp
struct S { 
    int x : 2; // int type treats high-order bit as sign
}; 

int main() { 
    S s; 
    s.x = 3; // warning C4463: overflow; assigning 3 
    // to bit-field that can only hold values from -2 to 1 
    // To fix, change assigned value to fit in range,
    // increase size of bitfield, and/or change base type 
    // to unsigned.
} 
```  
