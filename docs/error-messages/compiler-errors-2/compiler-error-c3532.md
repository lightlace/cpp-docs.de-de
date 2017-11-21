---
title: Compilerfehler C3532 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3532
dev_langs: C++
helpviewer_keywords: C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e78db21d00ea93378358a1147163276fb12bdfd5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3532"></a>Compilerfehler C3532
'Typ': falsche Verwendung von "Auto"  
  
 Der angegebene Typ kann nicht deklariert werden, mit dem `auto` Schlüsselwort. Angenommen, Sie können keine der `auto` -Schlüsselwort zu deklarieren, ein Array oder eine Methode Typ zurückgeben.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der Initialisierungsausdruck einen gültigen Typ ergibt.  
  
2.  Stellen Sie sicher, dass Sie ein Array oder ein Rückgabetyp der Methode nicht deklarieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3532 erzeugt, da die `auto` Schlüsselwort kann nicht der Rückgabetyp einer Methode deklariert werden.  
  
```  
// C3532a.cpp  
// Compile with /Zc:auto  
auto f(){}   // C3532  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3532 erzeugt, da die `auto` Schlüsselwort kann kein Array deklariert.  
  
```  
// C3532b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int x[5];  
   auto a[5];            // C3532  
   auto b[1][2];         // C3532  
   auto y[5] = x;        // C3532  
   auto z[] = {1, 2, 3}; // C3532  
   auto w[] = x;         // C3532  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)