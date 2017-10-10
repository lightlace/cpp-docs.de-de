---
title: Compilerfehler C2561 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2561
dev_langs:
- C++
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ce30ffb454deb7bc847e736458295d037826a0ad
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2561"></a>Compilerfehler C2561
'Bezeichner': Funktion muss einen Wert zurückgeben  
  
 Die Funktion wurde als Rückgabewert deklariert, aber der Definition der Funktion enthält keine `return` Anweisung.  
  
 Dieser Fehler kann durch einen falschen Funktionsprototyp verursacht werden:  
  
1.  Wenn die Funktion keinen Wert zurückgibt, deklarieren Sie die Funktion mit Rückgabetyp ["void"](../../cpp/void-cpp.md).  
  
2.  Überprüfen Sie, dass alle möglichen Verzweigungen der Funktion einen Wert des Typs im Prototyp deklariert zurückgibt.  
  
3.  C++-Funktionen mit Inline-Assembly-Routinen, die den Rückgabewert in speichern die `AX` Register möglicherweise eine return-Anweisung. Kopieren Sie den Wert in `AX` in eine temporäre Variable und diese Variable aus der Funktion zurückzugeben.  
  
 Im folgende Beispiel wird C2561 generiert:  
  
```  
// C2561.cpp  
int Test(int x) {  
   if (x) {  
      return;   // C2561  
      // try the following line instead  
      // return 1;  
   }  
   return 0;  
}  
  
int main() {  
   Test(1);  
}  
```
